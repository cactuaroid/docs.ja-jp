---
title: ICorDebugVariableSymbol::SetValue メソッド
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ccdb78e522cb037821135c52bf762707f7de76c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvariablesymbolsetvalue-method"></a>ICorDebugVariableSymbol::SetValue メソッド
バイト配列の値を変数に代入します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `offset`  
 [in] 値を設定する変数内の開始オフセットです。 このパラメーターは、オブジェクトのメンバー フィールドに書き込む際に使用されます。  
  
 `threadID`  
 [in] 新しい値を反映させるためにコンテキストを更新する必要があるスレッドのスレッド ID。  
  
 `cbContext`  
 [in] スレッド コンテキストのバイト単位のサイズ。  
  
 `context`  
 [in] 値の書き込みに使用されるスレッド コンテキスト。  
  
 `cbValue`  
 [in] `pValue` バッファーのバイト単位のサイズ。  
  
 `pValue`  
 [in] 設定する値が含まれるバッファー。  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメソッドは .NET ネイティブでのみ使用できます。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:** を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [ICorDebugVariableSymbol インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [デバッグ インターフェイス](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
