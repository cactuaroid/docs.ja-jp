---
title: 拡張メソッド
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15d36cc2d3073c9f695de81407ecabcd5e3bba30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574518"
---
# <a name="extension-methods"></a>拡張メソッド
拡張メソッドは、言語の機能により、インスタンス メソッドの呼び出し構文を使用して呼び出されるメソッドは静的です。 これらのメソッドは、操作するためには、メソッドのインスタンスを表すには、少なくとも 1 つのパラメーターを取得する必要があります。  
  
 このような拡張メソッドを定義するクラスが「スポンサー」クラスと呼ばれ、静的な宣言する必要があります。 拡張メソッドを使用するには、スポンサー クラスを定義する名前空間をインポートいずれかの必要があります。  
  
 **X AVOID** いないこと、お持ちでない型に特に拡張メソッドを定義します。  
  
 型のソース コードを所有する場合は、通常のインスタンス メソッドを代わりに使用することを検討します。 所有していない場合に、メソッドを追加するには、十分に注意します。 拡張メソッドを多めに使用では、これらのメソッドがあるように設計されていない種類の Api に混乱が生じる可能性があります。  
  
 **✓ CONSIDER** 拡張メソッドを使用して、次のシナリオのいずれかで。  
  
-   ヘルパーを提供するには、コア インターフェイスの観点から機能と言われます場合、インターフェイスのすべての実装に関連する機能を記述できます。 具体的な実装は、インターフェイスそれ以外の場合に割り当てることができないためにです。 たとえば、`LINQ to Objects`演算子がすべての拡張メソッドとして実装されて<xref:System.Collections.Generic.IEnumerable%601>型です。 したがって、いずれか`IEnumerable<>`実装が自動的に LINQ 有効にします。  
  
-   インスタンス メソッドがいくつかの型への依存関係が、このような依存関係をどのように発生する場合、依存関係の管理規則ができなくなります。 依存関係など、<xref:System.String>に<xref:System.Uri?displayProperty=nameWithType>が許容されない可能性がありますので`String.ToUri()`を返すインスタンス メソッド`System.Uri`依存関係の管理の観点から正しくないデザインになります。 拡張機能の静的メソッド`Uri.ToUri(this string str)`返す`System.Uri`量より優れた設計になります。  
  
 **X AVOID** で拡張メソッドを定義する<xref:System.Object?displayProperty=nameWithType>です。  
  
 VB のユーザーは拡張メソッド構文を使用してオブジェクト参照でこのようなメソッドを呼び出すことができません。 VB は vb の場合は参照を宣言するオブジェクトが遅延するすべてのメソッド呼び出しを強制的にバインドされているため、このようなメソッドの呼び出しをサポートしていません (と呼ばれる実際のメンバーは実行時に決定されます) 中、拡張メソッドへのバインドはコンパイル時 (早期に決定されますバインドされている)。  
  
 ガイドラインは、同じバインド動作が存在するその他の言語に適用されることに注意してください。 または、拡張メソッドはサポートされていません。  
  
 **X DO NOT** インターフェイスにメソッドを追加または依存関係の管理用である場合を除き、拡張の型と同じ名前空間の拡張メソッドを格納します。  
  
 **X AVOID** 異なる名前空間にある場合でも、同じシグネチャを持つ 2 つ以上の拡張メソッドを定義します。  
  
 **✓ CONSIDER** 型がインターフェイスで、ほとんどまたはすべてのケースで使用する拡張メソッドは、拡張された型と同じ名前空間に拡張メソッドを定義します。  
  
 **X DO NOT** 通常その他の機能に関連付けられている名前空間の機能を実装する拡張メソッドを定義します。 代わりに、所属する機能に関連付けられている名前空間で定義します。  
  
 **X AVOID** 拡張メソッド (たとえば、「拡張」) を専用の名前空間の汎用名前付けします。 わかりやすい名前 (たとえば、「ルーティング」) 代わりにします。  
  
 *部分 © 2005、2009 Microsoft Corporation します。All rights reserved.*  
  
 *ピアソン教育, Inc. からのアクセス許可によって検出[Framework デザイン ガイドライン: 規則、表現方法、および再利用可能な .NET ライブラリを第 2 版パターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)は Cwalina と Brad Abrams、2008 年 10 月 22 日で発行されました。Microsoft Windows 開発シリーズの一部として、Addison-wesley Professional。*  
  
## <a name="see-also"></a>関連項目  
 [メンバーのデザインのガイドライン](../../../docs/standard/design-guidelines/member.md)  
 [フレームワーク デザインのガイドライン](../../../docs/standard/design-guidelines/index.md)
