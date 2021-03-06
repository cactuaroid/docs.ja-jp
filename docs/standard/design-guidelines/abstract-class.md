---
title: 抽象クラスのデザイン
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28052cc6848d77acbdf8e9381146ca6fb06c15d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570566"
---
# <a name="abstract-class-design"></a>抽象クラスのデザイン
**X DO NOT** 抽象型の public または protected のコンス トラクター内部を定義します。  
  
 コンス トラクターは、ユーザーが型のインスタンスを作成する必要がある場合にのみ、パブリックにする必要があります。 抽象型のインスタンスを作成できないため、パブリック コンス トラクターを持つ抽象型が正しくされていない仕様であり、ユーザーに誤解を招く。  
  
 **✓ DO** 抽象クラス内で、保護されているか、内部のコンス トラクターを定義します。  
  
 プロテクト コンス トラクターより一般的なサブタイプが作成されるときに、独自の初期化を実行する基本クラスでは。  
  
 アセンブリのクラスを定義する抽象クラスの具象実装を制限する、内部のコンス トラクターを使用できます。  
  
 **✓ DO** を出荷する各の抽象クラスから継承する少なくとも 1 つの具象型を提供します。  
  
 抽象クラスの設計を検証するには、これによりを行っています。 たとえば、<xref:System.IO.FileStream?displayProperty=nameWithType>に実装されて、<xref:System.IO.Stream?displayProperty=nameWithType>抽象クラスです。  
  
 *部分 © 2005、2009 Microsoft Corporation します。All rights reserved.*  
  
 *ピアソン教育, Inc. からのアクセス許可によって検出[Framework デザイン ガイドライン: 規則、表現方法、および再利用可能な .NET ライブラリを第 2 版パターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)は Cwalina と Brad Abrams、2008 年 10 月 22 日で発行されました。Microsoft Windows 開発シリーズの一部として、Addison-wesley Professional。*  
  
## <a name="see-also"></a>関連項目  
 [型デザインのガイドライン](../../../docs/standard/design-guidelines/type.md)  
 [フレームワーク デザインのガイドライン](../../../docs/standard/design-guidelines/index.md)
