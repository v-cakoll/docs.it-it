---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 9984dc9c215a34ab35524560e4dcbcd6bd12596d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602845"
---
# <a name="datatablereaders"></a>DataTableReader
Il tipo <xref:System.Data.DataTableReader> presenta il contenuto di un tipo <xref:System.Data.DataTable> o di un tipo <xref:System.Data.DataSet> sotto forma di uno o più set di risultati forward-only in sola lettura.  
  
 Quando si crea una **DataTableReader** da un **DataTable**, risultante **DataTableReader** oggetto contiene un set di risultati con gli stessi dati il  **DataTable** da cui è stata creata, ad eccezione delle righe che sono state contrassegnate come eliminati. Le colonne sono visualizzate nello stesso ordine come originale **DataTable**.  
  
 Oggetto **DataTableReader** può contenere più set di risultati se è stato creato chiamando <xref:System.Data.DataSet.CreateDataReader%2A>. I risultati sono nello stesso ordine in cui il **DataTables** nel **set di dati** dell'oggetto <xref:System.Data.DataSet.Tables%2A> raccolta.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Viene illustrato come creare un **DataTableReader** oggetto.  
  
 [Esplorazione di oggetti DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Viene descritto come utilizzare il **lettura** metodo per scorrere il contenuto di un **DataTableReader**.  
  
## <a name="see-also"></a>Vedere anche
- [Recupero e modifica di dati in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
