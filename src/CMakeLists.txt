
set (volumetricRendererSrc 
		Util.cpp
		Main.cpp
		Image3D.cpp
		MainWindow.cpp
		HelperWidgets.cpp
		ControlPanel.cpp
		RenderViewport.cpp
		TestGenerateVolume.cpp
		SampleMappingEditor.cpp
		ImageSettings.cpp
		
		Renderer/Texture3D.cpp
		Renderer/Texture1D.cpp
		Renderer/Object3D.cpp
		Renderer/TextureVolumeObject.cpp
		Renderer/RayVolumeObject.cpp
		Renderer/CameraObject.cpp
		Renderer/CameraControl.cpp
		Renderer/AxisObject.cpp
		
		IO/Image3DFromDicomFile.cpp
		IO/Image3DFromTIFFFile.cpp
)

add_executable(VolumetricRenderer ${volumetricRendererSrc})

target_link_libraries(VolumetricRenderer Qt5::Core Qt5::Widgets Qt5::OpenGL)

target_link_libraries(VolumetricRenderer dcmdata dcmimgle dcmimage )

target_link_libraries(VolumetricRenderer tiff)