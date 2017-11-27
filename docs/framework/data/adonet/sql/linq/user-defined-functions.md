---
title: Funzioni definite dall'utente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ff13a123bcb2c61d786f2156e600a16cdd6bb31e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="user-defined-functions"></a>Funzioni definite dall'utente
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono usati metodi nel modello a oggetti per rappresentare funzioni definite dall'utente. Per definire i metodi come funzioni, applicare l'attributo <xref:System.Data.Linq.Mapping.FunctionAttribute> quindi, dove richiesto, l'attributo <xref:System.Data.Linq.Mapping.ParameterAttribute>. Per ulteriori informazioni, vedere [LINQ al modello a oggetti SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Per evitare un'eccezione <xref:System.InvalidOperationException>, è necessario che le funzioni definite dall'utente in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] siano in uno dei formati seguenti:  
  
-   Una funzione di cui è stato eseguito il wrapping come chiamata al metodo con gli attributi di mapping corretti. Per ulteriori informazioni, vedere [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
-   Un metodo SQL statico specifico di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
-   Una funzione supportata da un metodo [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].  
  
 Negli argomenti elencati in questa sezione viene illustrato come formare e chiamare questi metodi nell'applicazione quando si scrive codice personalizzato. Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] ricorrono in genere a [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per eseguire il mapping delle funzioni definite dall'utente.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: utilizzare funzioni definite dall'utente a valori scalari](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 Viene descritto come implementare una funzione che restituisce valori scalari.  
  
 [Procedura: utilizzare funzioni definite dall'utente con valori di tabella](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 Viene descritto come implementare una funzione che restituisce valori di tabella.  
  
 [Procedura: chiamare funzioni definite dall'utente Inline](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 Viene descritto come effettuare chiamate inline alle funzioni e le differenze di esecuzione quando viene effettuata la chiamata inline.
