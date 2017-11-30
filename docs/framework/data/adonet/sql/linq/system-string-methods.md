---
title: Metodi System.String
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3cfddba1bfa7bf7cefba917be0026b1c366f3513
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="systemstring-methods"></a>Metodi System.String
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportati i metodi <xref:System.String> riportati di seguito.  
  
## <a name="unsupported-systemstring-methods-in-general"></a>Metodi System.String non supportati in generale  
 Metodi <xref:System.String> non supportati in generale:  
  
-   Overload con il supporto delle impostazioni cultura (metodi che accettano un `CultureInfo`  /  `StringComparison`  /  `IFormatProvider`).  
  
-   Metodi che accettano o producono una matrice `char`.  
  
## <a name="unsupported-systemstring-static-methods"></a>Metodi System.String statici non supportati  
  
|Metodi System.String statici non supportati|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a>Metodi System.String non statici non supportati  
  
|Metodi System.String non statici non supportati|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a>Differenze rispetto a .NET  
  
-   Nelle query non vengono considerate le regole di confronto di SQL Server eventualmente attive sul server pertanto, per impostazione predefinita, verranno restituite regole di confronto dipendenti dalle impostazioni cultura e senza distinzione fra maiuscole e minuscole. Questo comportamento differisce dalla semantica predefinita con distinzione tra maiuscole e minuscole di .NET Framework.  
  
-   Quando `LastIndexOf` restituisce 0, la stringa è `NULL` o la posizione trovata è 0.  
  
-   È possibile che vengano restituiti risultati imprevisti dalla concatenazione o da altre operazioni sulle stringhe a lunghezza fissa (`CHAR`, `NCHAR`), poiché a questi tipi viene applicata automaticamente la spaziatura interna nel database.  
  
-   Poiché molti metodi, ad esempio `Replace`, `ToLower`, `ToUpper` e l'indicizzatore del carattere, non dispongono di una conversione valida per le colonne `TEXT` o `NTEXT` e XML, se vengono convertiti normalmente si verifica un'eccezione `SqlExceptions`. Questo comportamento viene considerato accettabile per questi tipi. Tuttavia è necessario che tutte le operazioni stringa corrispondano alla semantica Common Language Runtime (CLR) per `VARCHAR`, `NVARCHAR`, `VARCHAR(max)` e `NVARCHAR(max)`.  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni e tipi di dati](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
