---
title: OLE DB データ型のマッピング
ms.date: 03/30/2017
ms.assetid: 04bcb259-59d3-4fd7-894d-4f0dd0c68069
ms.openlocfilehash: 4287b125b26bc0c7233f59322c84e2ac27c0c594
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758933"
---
# <a name="ole-db-data-type-mappings"></a>OLE DB データ型のマッピング
.NET Framework Data Provider for ADO および OLE DB ([!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]) のデータ型から推論される <xref:System.Data.OleDb> の型を次の表に示します。 <xref:System.Data.OleDb.OleDbDataReader> の型指定されたアクセサー メソッドも示します。  
  
|ADO 型|OLE DB 型|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 型|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] の型指定されたアクセサー|  
|--------------|-----------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|adBigInt|DBTYPE_I8|Int64|GetInt64()|  
|adBinary|DBTYPE_BYTES|Byte[]|GetBytes()|  
|adBoolean|DBTYPE_BOOL|Boolean|GetBoolean()|  
|adBSTR|DBTYPE_BSTR|String|GetString()|  
|adChapter|DBTYPE_HCHAPTER|`DataReader` によってサポートされます。 参照してください[DataReader を使用してデータを取得する](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)です。|GetValue()|  
|adChar|DBTYPE_STR|String|GetString()|  
|adCurrency|DBTYPE_CY|Decimal (10 進数型)|GetDecimal()|  
|adDate|DBTYPE_DATE|DateTime|GetDateTime()|  
|adDBDate|DBTYPE_DBDATE|DateTime|GetDateTime()|  
|adDBTime|DBTYPE_DBTIME|DateTime|GetDateTime()|  
|adDBTimeStamp|DBTYPE_DBTIMESTAMP|DateTime|GetDateTime()|  
|adDecimal|DBTYPE_DECIMAL|Decimal (10 進数型)|GetDecimal()|  
|adDouble|DBTYPE_R8|Double (倍精度浮動小数点型)|GetDouble()|  
|adError|DBTYPE_ERROR|ExternalException|GetValue()|  
|adFileTime|DBTYPE_FILETIME|DateTime|GetDateTime()|  
|adGUID|DBTYPE_GUID|Guid|GetGuid()|  
|adIDispatch|DBTYPE_IDISPATCH *|Object|GetValue()|  
|adInteger|DBTYPE_I4|Int32|GetInt32()|  
|adIUnknown|DBTYPE_IUNKNOWN *|Object|GetValue()|  
|adNumeric|DBTYPE_NUMERIC|Decimal (10 進数型)|GetDecimal()|  
|adPropVariant|DBTYPE_PROPVARIANT|Object|GetValue()|  
|adSingle|DBTYPE_R4|Single|GetFloat()|  
|adSmallInt|DBTYPE_I2|Int16|GetInt16()|  
|adTinyInt|DBTYPE_I1|Byte|GetByte()|  
|adUnsignedBigInt|DBTYPE_UI8|UInt64|GetValue()|  
|adUnsignedInt|DBTYPE_UI4|UInt32|GetValue()|  
|adUnsignedSmallInt|DBTYPE_UI2|UInt16|GetValue()|  
|adUnsignedTinyInt|DBTYPE_UI1|Byte|GetByte()|  
|adVariant|DBTYPE_VARIANT|Object|GetValue()|  
|adWChar|DBTYPE_WSTR|String|GetString()|  
|adUserDefined|DBTYPE_UDT|サポート外||  
|adVarNumeric|DBTYPE_VARNUMERIC|サポート外||  
  
 \* OLE DB 型の`DBTYPE_IUNKNOWN`と`DBTYPE_IDISPATCH`、オブジェクト参照はポインターのマーシャ リングされた表現です。  
  
## <a name="see-also"></a>関連項目  
 [ADO.NET でのデータの取得および変更](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET のマネージ プロバイダーと DataSet デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=217917)
