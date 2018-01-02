---
title: DataTableReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0e3f3da6554239b4f04e244d3339a4280e1add85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="datatablereaders"></a>DataTableReader
Il tipo <xref:System.Data.DataTableReader> presenta il contenuto di un tipo <xref:System.Data.DataTable> o di un tipo <xref:System.Data.DataSet> sotto forma di uno o più set di risultati forward-only in sola lettura.  
  
 Quando si crea un **DataTableReader** da un **DataTable**, il valore risultante **DataTableReader** oggetto contiene un set di risultati con gli stessi dati il  **DataTable** da cui è stato creato, ad eccezione delle righe che sono state contrassegnate come eliminate. Le colonne vengono visualizzate nello stesso ordine utilizzato originale **DataTable**.  
  
 Oggetto **DataTableReader** può contenere più set di risultati, se è stato creato chiamando <xref:System.Data.DataSet.CreateDataReader%2A>. I risultati sono nello stesso ordine di **DataTable** nel **DataSet** dell'oggetto <xref:System.Data.DataSet.Tables%2A> insieme.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Viene illustrato come creare un **DataTableReader** oggetto.  
  
 [Esplorazione di oggetti DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Viene descritto come utilizzare il **lettura** metodo per scorrere il contenuto di un **DataTableReader**.  
  
## <a name="see-also"></a>Vedere anche  
 [Recupero e modifica di dati in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
