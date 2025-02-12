---
layout: default
title: Unity Addressable Assets and Scriptable Objects
parent: "2021-2023 Windwalker"
---

### Unity Addressable Assets and Scriptable Objects:

Unity has an asset management system that they built called Addressables. This is built on top of their original Asset Bundle structure and was intended to make the access of assets simpler and handle the memory management better. The theory was that we would load/unload assets as they were needed. 

Before this, we had primarily used lists or dictionaries that were pre-loaded in the editor with the assets. Then we would access them directly. This worked, but we wanted to try out the Addressable approach. Because the assets were pre-loaded, the memory was also pre-allocated for those assets, potentially using up resources for no reason.
