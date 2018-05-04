---
title: Dataset tipizzati
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 67c1d3a190c5a4f046d7c7da5ebbf98395a96341
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="typed-datasets"></a>Dataset tipizzati
Oltre all'accesso ad associazione tardiva ai valori tramite variabili tipizzate in modo debole, nel tipo <xref:System.Data.DataSet> è disponibile l'accesso ai dati tramite una metafora tipizzata in modo sicuro. Tabelle e colonne che fanno parte di **DataSet** sono accessibili mediante nomi descrittivi e variabili fortemente tipizzate.  
  
 Un oggetto tipizzato **DataSet** è una classe che deriva da un **DataSet**. In quanto tale, eredita tutti i metodi, eventi e proprietà di un **DataSet**. Inoltre, un oggetto tipizzato **DataSet** fornisce metodi fortemente tipizzati, proprietà ed eventi. È quindi possibile accedere mediante il nome alle tabelle e alle colonne, invece di usare metodi basati sulle raccolte. Oltre a una migliore leggibilità del codice, un oggetto tipizzato **DataSet** consente inoltre il codice di Visual Studio .NET editor per completare automaticamente le righe durante la digitazione.  
  
 Inoltre, l'oggetto fortemente tipizzato **DataSet** consente di accedere ai valori del tipo corretto in fase di compilazione. Con un oggetto fortemente tipizzato **DataSet**, gli errori di mancata corrispondenza di tipo vengono rilevati quando il codice viene compilato, anziché in fase di esecuzione.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Generazione di oggetti DataSet fortemente tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 Viene descritto come creare e usare un oggetto fortemente tipizzato **DataSet**.  
  
 [Annotazione di oggetti DataSet tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 Viene descritto come annotare lo schema XML Schema definition language (XSD) utilizzato per generare un oggetto fortemente tipizzato **DataSet**per assegnare **DataSet** nomi descrittivi di elementi senza alterare lo schema sottostante.  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
