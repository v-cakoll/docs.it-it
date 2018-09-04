---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: b3881ecfd895bd22a476bdac7dd0b7c1b112092e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526378"
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
 [Recupero e modifica di dati in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
