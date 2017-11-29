---
title: "CorDebugRecordFormat 列挙体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugRecordFormat
api_location: mscordbi.dll
api_type: COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c2f8397382dde061078a0d96114420f1c5f48669
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="11160-102">CorDebugRecordFormat 列挙体</span><span class="sxs-lookup"><span data-stu-id="11160-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="11160-103">ネイティブ例外デバッグ イベントに関する情報を格納するバイト配列内のデータの形式を示します。</span><span class="sxs-lookup"><span data-stu-id="11160-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11160-104">構文</span><span class="sxs-lookup"><span data-stu-id="11160-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="11160-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="11160-105">Members</span></span>  
  
|<span data-ttu-id="11160-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="11160-106">Member</span></span>|<span data-ttu-id="11160-107">説明</span><span class="sxs-lookup"><span data-stu-id="11160-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="11160-108">データは、32 ビット Windows 例外レコードです。</span><span class="sxs-lookup"><span data-stu-id="11160-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="11160-109">データは、64 ビット Windows 例外レコードです。</span><span class="sxs-lookup"><span data-stu-id="11160-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11160-110">コメント</span><span class="sxs-lookup"><span data-stu-id="11160-110">Remarks</span></span>  
 <span data-ttu-id="11160-111">メンバー、`CorDebugRecordFormat`に列挙体が渡される、 [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)メソッド内のバイト配列の形式を示すためにその`pRecord`引数。</span><span class="sxs-lookup"><span data-stu-id="11160-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11160-112">この列挙体は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="11160-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11160-113">要件</span><span class="sxs-lookup"><span data-stu-id="11160-113">Requirements</span></span>  
 <span data-ttu-id="11160-114">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="11160-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11160-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11160-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11160-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11160-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11160-117">**.NET framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11160-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11160-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="11160-118">See Also</span></span>  
 [<span data-ttu-id="11160-119">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="11160-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)