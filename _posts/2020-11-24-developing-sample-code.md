---
title: Handling Assets
description: 15
---

<p><strong>1.Create an instance from HwAssetManager. We will use this instance for all asset operations</strong></p>
<pre><div id="copy-button10" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>  private val hwAssetManager = HwAssetManager.getInstance()   
<span class="pln">
</span></code></pre>


<p><strong>2.Asset Insert</strong></p>
<pre><div id="copy-button11" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>  fun insertData(bundle: Bundle){
        val result  = hwAssetManager.assetInsert(context, bundle)
        if (result.resultCode == HwAssetManager.SUCCESS) {
            Toast.makeText(context,"Your asset successfully inserted: " + result.resultInfo[0], Toast.LENGTH_SHORT).show()
        }else
            onFailure(result,"Asset Insert")
    }
<span class="pln">
</span></code></pre>


<p><strong>3.Asset Update</strong></p>
<pre><div id="copy-button11" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>  fun updateData (bundle: Bundle) {
        val result  = hwAssetManager.assetInsert(context, bundle)
        if (result.resultCode == HwAssetManager.SUCCESS) {
            Toast.makeText(context,"Your asset successfully updated: " + result.resultInfo[0], Toast.LENGTH_SHORT).show()
        }else
            onFailure(result,"Asset Update")
    }
<span class="pln">
</span></code></pre>


<p><strong>4.Asset Select</strong></p>
<pre><div id="copy-button11" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>   fun selectData(bundle: Bundle) :ArrayList<AssetModel>{
        val result = hwAssetManager.assetSelect(context,bundle)
        if (result.resultCode == HwAssetManager.SUCCESS) {
            Toast.makeText(context,"Your asset successfully selected: " + result.resultInfo[0], Toast.LENGTH_SHORT).show()
            val gson = Gson()
            val list: ArrayList<AssetModel> = arrayListOf()
            for (i in result.resultInfo) {
                list.add(gson.fromJson(i, AssetModel::class.java))
            }
            return list
        }else {
            onFailure(result,"Asset Select")
        }
         return arrayListOf()
      
    }
    
<span class="pln">
</span></code></pre>


<p><strong>5.Asset Delete</strong></p>
<pre><div id="copy-button11" class="copy-btn" title="Copy" onclick="copyCode(this.id)"></div><code>   fun deleteData(bundle: Bundle) {
        val result = hwAssetManager.assetDelete(context,bundle)
         if (result.resultCode == HwAssetManager.SUCCESS){
             Toast.makeText(context,"Your asset successfully deleted: " + result.resultInfo[0], Toast.LENGTH_SHORT).show()
        }else {
             onFailure(result, "Asset Delete")
        }
    }
<span class="pln">
</span></code></pre>
