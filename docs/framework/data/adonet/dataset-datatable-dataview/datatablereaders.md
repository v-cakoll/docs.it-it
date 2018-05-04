---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 8305629bb267805cd79455e2edf990e72a12dc10
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
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
