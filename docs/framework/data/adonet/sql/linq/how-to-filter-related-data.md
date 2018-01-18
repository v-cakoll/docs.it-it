---
title: 'Procedura: filtrare dati correlati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 27c09badda5675158ca5c50481472db142eca32e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-filter-related-data"></a>Procedura: filtrare dati correlati
Usare il metodo <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> per specificare sottoquery che consentano di limitare la quantità di dati recuperati.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente il metodo <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> limita il numero di `Orders` recuperati a quelli non spediti in data odierna. Senza questo approccio verrebbero recuperati tutti gli elementi in `Orders`, anche se è richiesto solo un subset.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esecuzione di query sul database](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
