# Antidetect browser MacOS Linux Windows 

### https://disk.yandex.ru/d/QXuCZs1MC5T3FQ архив на chrome
### https://disk.yandex.ru/d/XRlwhl3yipstsw архив на профиль

### запуск chrome --user-data-dir="path to profile1"

файл профиля (отпечатка) pref.json должен лежать в Default он ужек там лежит, вы можете его открыть и ознакомится

## Configuration File Description

Описание настроек профиля

### `profile`
- `id`: ID профиля 
- `name`: Имя профиля будет отображаться в иконке в taskbar и в адресной строке в LocationIconView::GetText

#### Geographic Information (`geo`) 
- `accuracy`: подмена гео координат third_party/blink/renderer/modules/geolocation/geolocation.cc
- `latitude`: подмена гео координат 
- `longitude`: подмена гео координат 
- `acceptLanguage`: подмена языка content/browser/renderer_host/navigation_request.cc
- `langs`: подмена языка net/http/http_util.cc, components/reduce_accept_language/browser/reduce_accept_language_service.cc
- `lang`: подмена языка third_party/blink/renderer/core/frame/navigator_language.cc
- `timeZone`: подмена таймзоны
- `country`: подмена таймзоны

#### Switches (`switches`)
- `webglSwitch`: включить подмену webgl (renderer vendor) "third_party/blink/renderer/modules/webgl/webgl_rendering_context_base.cc", 
- `webGpuSwitch`: включить подмену webgpu  renderer/modules/webgpu/gpu_adapter.cc
- `trackSwitch`: включить подмену DNT 
- `canvasNoiseSwitch`: включить подмену canvas шум third_party\blink\renderer\core\html\canvas\canvas_async_blob_creator.cc, third_party\blink\renderer\modules\canvas\canvas2d\base_rendering_context_2d.cc,third_party\blink\renderer\platform\graphics\image_data_buffer.cc, third_party\blink\renderer\platform\graphics\static_bitmap_image.cc
- `webglNoiseSwitch`: включить подмену webgl шум gpu/command_buffer/client/gles2_implementation.cc
- `webRtcSwitch`: включить подмену webrtc IP при использовании прокси https://browserleaks.com/webrtc public address

#### Fingerprint Information (`fp`)
- `userAgent`: user-agent content/common/user_agent.cc
- `hardwareConcurrency`: third_party/blink/renderer/core/frame/navigator_concurrent_hardware.cc
- `deviceMemory`: third_party/blink/common/device_memory/approximated_device_memory.cc
- `widthScreen`: не используется
- `heightScreen`: не используется
- `mediaDevices`: медиа девайсес third_party/blink/renderer/modules/mediastream/media_devices.cc
- `webGpu`: значение webgpu
- `webRtc`: third_party\webrtc\p2p\base\stun_port.cc
- `renderer`: при включенном webGpuSwitch RendererBlinkPlatformImpl::Collect3DContextInformation
- `vendor`: при включенном webGpuSwitch RendererBlinkPlatformImpl::Collect3DContextInformation
- `platform`: third_party/blink/renderer/core/execution_context/navigator_base.cc , /third_party/blink/renderer/core/frame/navigator_id.cc, 
- `userAgentData`: [Description] components/embedder_support/user_agent_utils.cc user_agent_utils.cc::GetUserAgentMetadata
    - `brands`: значение ua
    - `fullVersionList`: значение ua
    - `platform`: значение ua
    - `platformVersion`: значение ua
    - `uaFullVersion`: значение ua
    - `wow64`: значение ua
    - `architecture`:значение ua
    - `bitness`: значение ua
    - `model`: значение ua
    - `mobile`: значение ua
- `speech`: подмена голосовых помошников content/browser/speech/tts_win.cc, content/browser/speech/tts_mac.cc
- `noisePercentage`: коэфф шума для каждого профиля

#### Proxy Settings (`proxy`)
- `login`: логин  для прокси
- `password`: пароль для прокси
- `ip`: адресс на который поменяется webrtc подмена(todo сделать автоматом проверку адреса на выходе и подменять автоматом)


###  Human typing

Также работает Human typing из контекстного меню вставляет строку из буфера обмена с рандомной задержкой, имитируя набор клавиш человеком,
практиковался работать с кликами и нажатием клавиш из самого браузера.

### подмена getClientRects реализована в 

 third_party/blink/renderer/core/dom/document.cc 
 third_party/blink/renderer/core/dom/document.h 
 third_party/blink/renderer/core/dom/element.cc
 third_party/blink/renderer/core/dom/range.cc 

### Battery spoof реализована в 

third_party/blink/renderer/modules/battery/battery_manager.cc
