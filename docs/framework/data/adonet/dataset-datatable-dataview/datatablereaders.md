---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1ff7868b59c6fdc4e6c443be1b831accc84f36a6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203813"
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
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
