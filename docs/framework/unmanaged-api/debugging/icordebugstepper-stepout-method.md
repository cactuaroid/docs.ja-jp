---
title: "ICorDebugStepper::StepOut メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepOut
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b3ceca69b6b4710a3f1b8e1e9bdb4baf574119c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="490b1-102">ICorDebugStepper::StepOut メソッド</span><span class="sxs-lookup"><span data-stu-id="490b1-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="490b1-103">Icordebugstepper シングル ステップ実行に現在のフレームが呼び出し元のフレームに制御を返すときに完了してその格納スレッドを表示します。</span><span class="sxs-lookup"><span data-stu-id="490b1-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="490b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="490b1-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="490b1-105">コメント</span><span class="sxs-lookup"><span data-stu-id="490b1-105">Remarks</span></span>  
 <span data-ttu-id="490b1-106">A`StepOut`呼び出し元のフレームを現在のフレームから正常に返る後に操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="490b1-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="490b1-107">場合`StepOut`時に呼び出される、現在のフレームが呼び出し元のマネージ コードに戻るときに、アンマネージ コードでステップを行います。</span><span class="sxs-lookup"><span data-stu-id="490b1-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="490b1-108">.NET Framework version 2.0 では使用しないで`StepOut`STOP_UNMANAGED フラグをセットが失敗するためです。</span><span class="sxs-lookup"><span data-stu-id="490b1-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="490b1-109">(使用[icordebugstepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)ステッピングのフラグを設定します)。相互運用機能デバッガー必要があります [ステップ アウト] ネイティブ コードに自体です。</span><span class="sxs-lookup"><span data-stu-id="490b1-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="490b1-110">要件</span><span class="sxs-lookup"><span data-stu-id="490b1-110">Requirements</span></span>  
 <span data-ttu-id="490b1-111">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="490b1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="490b1-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="490b1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="490b1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="490b1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="490b1-114">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="490b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>