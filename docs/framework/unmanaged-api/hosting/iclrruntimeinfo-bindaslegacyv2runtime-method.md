---
title: "ICLRRuntimeInfo::BindAsLegacyV2Runtime メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 229c5483c02357054f3d2821d8e024c78887e839
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="6888a-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime メソッド</span><span class="sxs-lookup"><span data-stu-id="6888a-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="6888a-103">すべてレガシ共通言語ランタイム (CLR) バージョン 2 のアクティブ化ポリシーの決定の現在のランタイムにバインドします。</span><span class="sxs-lookup"><span data-stu-id="6888a-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6888a-104">構文</span><span class="sxs-lookup"><span data-stu-id="6888a-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6888a-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="6888a-105">Return Value</span></span>  
 <span data-ttu-id="6888a-106">このメソッドは、次の特定の Hresult を返します。</span><span class="sxs-lookup"><span data-stu-id="6888a-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="6888a-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6888a-107">HRESULT</span></span>|<span data-ttu-id="6888a-108">説明</span><span class="sxs-lookup"><span data-stu-id="6888a-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6888a-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="6888a-109">S_OK</span></span>|<span data-ttu-id="6888a-110">バインディングが成功したか、このランタイムがレガシ CLR バージョン 2 のアクティブ化のポリシー実行時に既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="6888a-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="6888a-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="6888a-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="6888a-112">異なるランタイムは、従来の CLR バージョン 2 のアクティブ化ポリシーに既にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="6888a-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6888a-113">コメント</span><span class="sxs-lookup"><span data-stu-id="6888a-113">Remarks</span></span>  
 <span data-ttu-id="6888a-114">現在のランタイムがすべてレガシ CLR バージョン 2 のアクティブ化ポリシーの決定に既にバインドされている場合 (たとえばを使用して、`useLegacyV2RuntimeActivationPolicy`属性を[\<スタートアップ > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)構成ファイルで)、このメソッドエラーの結果を返しません代わりと同様、メソッドがレガシ アクティブ化ポリシーを正常にバインドしたかどうかに、結果は S_OK です。</span><span class="sxs-lookup"><span data-stu-id="6888a-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6888a-115">要件</span><span class="sxs-lookup"><span data-stu-id="6888a-115">Requirements</span></span>  
 <span data-ttu-id="6888a-116">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="6888a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6888a-117">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6888a-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6888a-118">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="6888a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6888a-119">**.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6888a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6888a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6888a-120">See Also</span></span>  
 [<span data-ttu-id="6888a-121">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6888a-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="6888a-122">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6888a-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="6888a-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="6888a-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="6888a-124">\<スタートアップ > 要素</span><span class="sxs-lookup"><span data-stu-id="6888a-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)