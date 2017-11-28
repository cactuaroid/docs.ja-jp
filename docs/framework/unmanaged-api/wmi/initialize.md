---
title: "Initialize 関数 (アンマネージ API リファレンス)"
description: "初期化関数は、WMI の初期化を実行します。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Initialize
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Initialize
helpviewer_keywords: Initialize function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ed0e0127608f9f80a2661067dd9a6025fd579a7
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="initialize-function"></a><span data-ttu-id="6bab8-103">Initialize 関数</span><span class="sxs-lookup"><span data-stu-id="6bab8-103">Initialize function</span></span>
<span data-ttu-id="6bab8-104">WMI の初期化を実行します。</span><span class="sxs-lookup"><span data-stu-id="6bab8-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6bab8-105">構文</span><span class="sxs-lookup"><span data-stu-id="6bab8-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="6bab8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6bab8-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="6bab8-107">[in]`true` WMI オブジェクトでの queryinterface 呼び出しが許可されるを示すために`false`それ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="6bab8-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="6bab8-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="6bab8-108">Return value</span></span>

<span data-ttu-id="6bab8-109">関数は常に返します`S_OK`(0) です。</span><span class="sxs-lookup"><span data-stu-id="6bab8-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="6bab8-110">要件</span><span class="sxs-lookup"><span data-stu-id="6bab8-110">Requirements</span></span>  
 <span data-ttu-id="6bab8-111">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="6bab8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bab8-112">**ヘッダー:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="6bab8-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="6bab8-113">**.NET framework のバージョン:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6bab8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bab8-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bab8-114">See also</span></span>  
[<span data-ttu-id="6bab8-115">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6bab8-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)