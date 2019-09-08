---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1559cde9cb786ccb2baf920347064b8b28d472c3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785353"
---
# <a name="datatablereaders"></a>DataTableReader
Il tipo <xref:System.Data.DataTableReader> presenta il contenuto di un tipo <xref:System.Data.DataTable> o di un tipo <xref:System.Data.DataSet> sotto forma di uno o più set di risultati forward-only in sola lettura.  
  
 Quando si crea un **DataTableReader** da una **DataTable**, l'oggetto **DataTableReader** risultante contiene un set di risultati con gli stessi dati del **DataTable** da cui è stato creato, ad eccezione delle righe contrassegnate come eliminato. Le colonne vengono visualizzate nello stesso ordine in cui si trova nella **DataTable**originale.  
  
 Un **DataTableReader** può contenere più set di <xref:System.Data.DataSet.CreateDataReader%2A>risultati se è stato creato chiamando. I risultati sono nello stesso ordine delle **DataTable** nella <xref:System.Data.DataSet.Tables%2A> raccolta dell'oggetto **DataSet** .  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataReader](creating-a-datareader.md)  
 Viene illustrato come creare un oggetto **DataTableReader** .  
  
 [Esplorazione di oggetti DataTable](navigating-datatables.md)  
 Viene descritto l'utilizzo del metodo **Read** per spostarsi nel contenuto di un **DataTableReader**.  
  
## <a name="see-also"></a>Vedere anche

- [Recupero e modifica di dati in ADO.NET](../retrieving-and-modifying-data.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
