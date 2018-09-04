---
title: Dataset tipizzati
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 68721bcdbce6bf6d3279d6018ce6bc48d65c55a3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43536801"
---
# <a name="typed-datasets"></a>Dataset tipizzati
Oltre all'accesso ad associazione tardiva ai valori tramite variabili tipizzate in modo debole, nel tipo <xref:System.Data.DataSet> è disponibile l'accesso ai dati tramite una metafora tipizzata in modo sicuro. Tabelle e colonne che fanno parte del **set di dati** sono accessibili tramite nomi descrittivi e variabili fortemente tipizzate.  
  
 Un oggetto tipizzato **set di dati** è una classe che deriva da una **DataSet**. In quanto tale, eredita tutti i metodi, eventi e le proprietà di un **set di dati**. Inoltre, un oggetto tipizzato **set di dati** fornisce metodi fortemente tipizzati, proprietà ed eventi. È quindi possibile accedere mediante il nome alle tabelle e alle colonne, invece di usare metodi basati sulle raccolte. A parte di una migliore leggibilità del codice, un oggetto tipizzato **set di dati** consente inoltre il codice di Visual Studio .NET dell'editor completare automaticamente le righe durante la digitazione.  
  
 Inoltre, l'oggetto fortemente tipizzato **set di dati** fornisce accesso ai valori del tipo corretto in fase di compilazione. Con una classe fortemente tipizzata **set di dati**, gli errori di mancata corrispondenza di tipo vengono rilevati quando il codice viene compilato, anziché in fase di esecuzione.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Generazione di oggetti DataSet fortemente tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 Viene descritto come creare e usare un oggetto fortemente tipizzato **set di dati**.  
  
 [Annotazione di oggetti DataSet tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 Viene descritto come annotare lo schema XML Schema definition language (XSD) utilizzato per generare una classe fortemente tipizzata **set di dati**per assegnare **DataSet** nomi descrittivi di elementi senza alterare lo schema sottostante.  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
