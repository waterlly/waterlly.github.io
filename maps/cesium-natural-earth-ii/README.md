# Cesium 仓库全球底图下载

资源：CesiumJS 随附的 Natural Earth II 全球影像，42 张 256×256 JPEG 瓦片，级别 0–2，最高级全球网格 8×4（等效 2048×1024）。完整下载含 `tilemapresource.xml` 共 43 个上游数据文件，475,959 字节。

来源仓库：https://github.com/CesiumGS/cesium

固定提交：`e1d443e8fdaae0535407b96f7560426583483424`

上游路径：`packages/engine/Source/Assets/Textures/NaturalEarthII/`

`source.json` 记录每个文件的上游 Git blob SHA-1、SHA-256 和大小；下载时逐个核对。`CESIUM-LICENSE.md` 保留该提交的 Cesium 许可证。Natural Earth 原始地图数据属于公有领域，参见 https://www.naturalearthdata.com/about/terms-of-use/ 。

本地服务地址：`http://localhost:3000/maps/cesium-natural-earth-ii/`。可打开 `preview.html` 预览全球底图。

这是离线低分辨率影像，没有地面高程、高清卫星影像、建筑或真实机场。当前飞行器仍使用原有本地演示机场；仅下载资源不会把飞行场景自动转换成真实全球地景。

Cesium 官方离线资源说明：https://github.com/CesiumGS/cesium/blob/main/Documentation/OfflineGuide/README.md
