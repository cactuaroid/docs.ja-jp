---
title: "IMetaDataAssemblyEmit::DefineAssemblyRef メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssemblyRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 074e589b84e21de4ec3bcc3c54a865297587d383
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="5bc47-102">IMetaDataAssemblyEmit::DefineAssemblyRef メソッド</span><span class="sxs-lookup"><span data-stu-id="5bc47-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="5bc47-103">このアセンブリが参照するアセンブリのメタデータを含む `AssemblyRef` 構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="5bc47-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bc47-104">構文</span><span class="sxs-lookup"><span data-stu-id="5bc47-104">Syntax</span></span>  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bc47-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5bc47-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="5bc47-106">[in]参照先アセンブリの発行者の公開キー。</span><span class="sxs-lookup"><span data-stu-id="5bc47-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="5bc47-107">ヘルパー関数[StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)このパラメーターとして渡すための公開キーのハッシュを取得するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5bc47-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="5bc47-108">[in]バイト サイズ`pbPublicKeyOrToken`です。</span><span class="sxs-lookup"><span data-stu-id="5bc47-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="5bc47-109">[in]アセンブリの人間が判読できるテキストの名前。</span><span class="sxs-lookup"><span data-stu-id="5bc47-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="5bc47-110">この値は 1024 文字を超えない必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc47-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="5bc47-111">[in]参照されたアセンブリのバージョン、プラットフォーム、およびロケール情報を含む ASSEMBLYMETADATA インスタンス。</span><span class="sxs-lookup"><span data-stu-id="5bc47-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="5bc47-112">[in]参照されたアセンブリに関連付けられているデータをハッシュします。</span><span class="sxs-lookup"><span data-stu-id="5bc47-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="5bc47-113">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5bc47-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="5bc47-114">[in]バイト サイズ`pbHashValue`です。</span><span class="sxs-lookup"><span data-stu-id="5bc47-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="5bc47-115">[in]ビットごとの組み合わせ[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)実行エンジンの動作を決定する値。</span><span class="sxs-lookup"><span data-stu-id="5bc47-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="5bc47-116">[out]返されたへのポインター`AssemblyRef`メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="5bc47-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bc47-117">コメント</span><span class="sxs-lookup"><span data-stu-id="5bc47-117">Remarks</span></span>  
 <span data-ttu-id="5bc47-118">1 つ`AssemblyRef`このアセンブリが参照する各アセンブリのメタデータ構造体を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc47-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="5bc47-119">実行時に、参照先アセンブリの詳細については、"組み込み"として情報を表すことを示す値をアセンブリの競合回避モジュールに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5bc47-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="5bc47-120">アセンブリ リゾルバーは、ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="5bc47-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bc47-121">要件</span><span class="sxs-lookup"><span data-stu-id="5bc47-121">Requirements</span></span>  
 <span data-ttu-id="5bc47-122">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="5bc47-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bc47-123">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5bc47-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5bc47-124">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="5bc47-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5bc47-125">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bc47-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc47-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bc47-126">See Also</span></span>  
 [<span data-ttu-id="5bc47-127">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5bc47-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)