---
title: 'Procedura: rappresentare colonne calcolate'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: eef3d12d3b0baa849d8eee1a01a87e3c6eee1c7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-computed-columns"></a>Procedura: rappresentare colonne calcolate
Utilizzare il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> proprietà in un <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per rappresentare una colonna il cui contenuto è il risultato del calcolo.  
  
 Per esempi di codice, vedere <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
>  In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportate colonne calcolate come chiavi primarie.  
  
### <a name="to-represent-a-computed-column"></a>Per rappresentare una colonna calcolata  
  
1.  Aggiungere la proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> all'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Assegnare una rappresentazione di stringa della formula alla proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ to SQL modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Procedura: personalizzare classi di entità utilizzando l'Editor di codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
