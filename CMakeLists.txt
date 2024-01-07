cmake_minimum_required(VERSION 3.20)
project(Example VERSION 0.1.0 LANGUAGES CSharp)

include(CSharpUtilities)

add_executable(Example
	App.config
	App.xaml
	App.xaml.cs
	MainWindow.xaml
	MainWindow.xaml.cs

	Properties/AssemblyInfo.cs)

csharp_set_designer_cs_properties(
	Properties/AssemblyInfo.cs)

csharp_set_xaml_cs_properties(
	App.xaml
	App.xaml.cs
	MainWindow.xaml
	MainWindow.xaml.cs)

set_property(SOURCE App.xaml PROPERTY VS_XAML_TYPE "ApplicationDefinition")

set_property(TARGET Example PROPERTY DOTNET_SDK "Microsoft.NET.Sdk")
set_property(TARGET Example PROPERTY DOTNET_TARGET_FRAMEWORK "net6.0")

set_property(TARGET Example PROPERTY WIN32_EXECUTABLE TRUE)

#set_property(
#  TARGET Example
#  PROPERTY VS_PACKAGE_REFERENCES
#  "Microsoft.WindowsAppSDK_1.4.230913002"
#  "Microsoft.Windows.SDK.BuildTools_10.0.22621.755"
#)