cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 14)

project(playfab)

file(GLOB PF_SOURCE code/source/playfab/*.cpp code/source/playfab/QoS/*.cpp code/*.cpp)

include_directories(code/include)
include_directories(code)

add_definitions(-DENABLE_PLAYFABADMIN_API -DENABLE_PLAYFABSERVER_API)

add_library(playfab code/stdafx.cpp
	                code/source/playfab/PlayFabAuthenticationContext.cpp
					code/source/playfab/PlayFabApiSettings.cpp
					code/source/playfab/PlayFabAdminApi.cpp
					code/source/playfab/PlayFabAdminInstanceApi.cpp
					code/source/playfab/PlayFabClientApi.cpp
					code/source/playfab/PlayFabClientInstanceApi.cpp
                    code/source/playfab/PlayFabMatchmakerApi.cpp
                    code/source/playfab/PlayFabMatchmakerInstanceApi.cpp
                    code/source/playfab/PlayFabServerApi.cpp
                    code/source/playfab/PlayFabServerInstanceApi.cpp
                    code/source/playfab/PlayFabAuthenticationApi.cpp
                    code/source/playfab/PlayFabAuthenticationInstanceApi.cpp
                    code/source/playfab/PlayFabCloudScriptApi.cpp
                    code/source/playfab/PlayFabCloudScriptInstanceApi.cpp
                    code/source/playfab/PlayFabDataApi.cpp
                    code/source/playfab/PlayFabDataInstanceApi.cpp
                    code/source/playfab/PlayFabEventsApi.cpp
                    code/source/playfab/PlayFabEventsInstanceApi.cpp
                    code/source/playfab/PlayFabExperimentationApi.cpp
                    code/source/playfab/PlayFabExperimentationInstanceApi.cpp
                    code/source/playfab/PlayFabInsightsApi.cpp
                    code/source/playfab/PlayFabInsightsInstanceApi.cpp
                    code/source/playfab/PlayFabGroupsApi.cpp
                    code/source/playfab/PlayFabGroupsInstanceApi.cpp
                    code/source/playfab/PlayFabLocalizationApi.cpp
                    code/source/playfab/PlayFabLocalizationInstanceApi.cpp
                    code/source/playfab/PlayFabMultiplayerApi.cpp
                    code/source/playfab/PlayFabMultiplayerInstanceApi.cpp
                    code/source/playfab/PlayFabProfilesApi.cpp
                    code/source/playfab/PlayFabProfilesInstanceApi.cpp
                    code/source/playfab/PlayFabCallRequestContainer.cpp
                    code/source/playfab/PlayFabCallRequestContainerBase.cpp
                    code/source/playfab/PlayFabError.cpp
                    code/source/playfab/PlayFabCurlHttpPlugin.cpp
                    code/source/playfab/PlayFabPluginManager.cpp
                    code/source/playfab/PlayFabSettings.cpp
                    code/source/playfab/PlayFabEvent.cpp
                    code/source/playfab/PlayFabEventApi.cpp
                    code/source/playfab/PlayFabEventBuffer.cpp
                    code/source/playfab/PlayFabEventPipeline.cpp
                    code/source/playfab/PlayFabEventRouter.cpp
                    code/source/playfab/PlayFabSpinLock.cpp
                    code/source/playfab/QoS/RegionResult.cpp
                    code/source/playfab/QoS/PlayFabQoSApi.cpp
                    code/source/playfab/QoS/QoSSocket.cpp
                    code/source/playfab/QoS/XPlatSocket.cpp)

# Requires installation of libjsoncpp-dev, libcurl4-openssl-dev
target_link_libraries(playfab -ljsoncpp -lcurl -lpthread)
