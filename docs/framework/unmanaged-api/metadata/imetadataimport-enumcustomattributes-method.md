---
title: "IMetaDataImport::EnumCustomAttributes メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumCustomAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 78a642ab3c9766ba32537e24814b3b0536df67c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="ec0f6-102">IMetaDataImport::EnumCustomAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="ec0f6-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="ec0f6-103">指定した型またはメンバーに関連付けられているカスタム属性定義トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec0f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="ec0f6-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec0f6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec0f6-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ec0f6-106">[入力、出力].返された列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="ec0f6-107">[in]列挙体、またはすべてのカスタム属性に 0 のスコープのトークンです。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="ec0f6-108">[in]列挙する属性の型のコンス トラクターのトークンまたは`null`すべての種類。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="ec0f6-109">[out]トークンのカスタム属性の配列。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ec0f6-110">[in] `rCustomAttributes` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="ec0f6-111">[out, 省略可能]実際に返されるトークンの値の数`rCustomAttributes`です。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec0f6-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="ec0f6-112">Return Value</span></span>  
  
|<span data-ttu-id="ec0f6-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec0f6-113">HRESULT</span></span>|<span data-ttu-id="ec0f6-114">説明</span><span class="sxs-lookup"><span data-stu-id="ec0f6-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ec0f6-115">`EnumCustomAttributes`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ec0f6-116">列挙するカスタム属性はありません。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="ec0f6-117">その場合は、`pcCustomAttributes`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec0f6-118">要件</span><span class="sxs-lookup"><span data-stu-id="ec0f6-118">Requirements</span></span>  
 <span data-ttu-id="ec0f6-119">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec0f6-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ec0f6-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec0f6-121">**ライブラリ:** MsCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec0f6-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec0f6-122">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec0f6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec0f6-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec0f6-123">See Also</span></span>  
 [<span data-ttu-id="ec0f6-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec0f6-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ec0f6-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec0f6-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)