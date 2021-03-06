---
title: プロテクト メンバー
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4d334d9809f374442e19807d3b249a17a1d9df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571086"
---
# <a name="protected-members"></a>プロテクト メンバー
単独で保護されたメンバーはすべての機能拡張を指定しないがサブクラス化によって拡張機能をより強力な行うことができます。 メインのパブリック インターフェイスを不必要に複雑化せず、高度なカスタマイズ オプションを公開に使用できます。  
  
 フレームワークの設計者は、「保護された」名前が false 安心感を与えることができますので、プロテクト メンバーには注意する必要があります。 すべてのユーザーはサブクラス封印されていないクラスとメンバーへのアクセスが保護されているをできるパブリック メンバーに使用された守勢のコーディング方法が保護されたメンバーに適用するためすべて同じです。  
  
 **✓ CONSIDER** 高度なカスタマイズのメンバーを使用して保護されています。  
  
 **✓ DO** セキュリティ、ドキュメント、および互換性分析するためにパブリックと封印されていないクラスにプロテクト メンバーを処理します。  
  
 クラスから継承するすべてのユーザーし、プロテクト メンバーにアクセスできます。  
  
 *部分 © 2005、2009 Microsoft Corporation します。All rights reserved.*  
  
 *ピアソン教育, Inc. からのアクセス許可によって検出[Framework デザイン ガイドライン: 規則、表現方法、および再利用可能な .NET ライブラリを第 2 版パターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)は Cwalina と Brad Abrams、2008 年 10 月 22 日で発行されました。Microsoft Windows 開発シリーズの一部として、Addison-wesley Professional。*  
  
## <a name="see-also"></a>関連項目  
 [フレームワーク デザインのガイドライン](../../../docs/standard/design-guidelines/index.md)  
 [機能拡張のデザイン](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
