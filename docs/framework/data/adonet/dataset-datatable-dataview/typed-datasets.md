---
title: Dataset tipizzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e3d5edc4f469b59ff787e500ad447fe0076c332c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="typed-datasets"></a>Dataset tipizzati
Oltre all'accesso ad associazione tardiva ai valori tramite variabili tipizzate in modo debole, nel tipo <xref:System.Data.DataSet> è disponibile l'accesso ai dati tramite una metafora tipizzata in modo sicuro. Tabelle e colonne che fanno parte di **DataSet** sono accessibili mediante nomi descrittivi e variabili fortemente tipizzate.  
  
 Un oggetto tipizzato **DataSet** è una classe che deriva da un **DataSet**. In quanto tale, eredita tutti i metodi, eventi e proprietà di un **DataSet**. Inoltre, un oggetto tipizzato **DataSet** fornisce metodi fortemente tipizzati, proprietà ed eventi. È quindi possibile accedere mediante il nome alle tabelle e alle colonne, invece di usare metodi basati sulle raccolte. Oltre a una migliore leggibilità del codice, un oggetto tipizzato **DataSet** consente inoltre il codice di Visual Studio .NET editor per completare automaticamente le righe durante la digitazione.  
  
 Inoltre, l'oggetto fortemente tipizzato **DataSet** consente di accedere ai valori del tipo corretto in fase di compilazione. Con un oggetto fortemente tipizzato **DataSet**, gli errori di mancata corrispondenza di tipo vengono rilevati quando il codice viene compilato, anziché in fase di esecuzione.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Generazione di DataSet fortemente tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 Viene descritto come creare e usare un oggetto fortemente tipizzato **DataSet**.  
  
 [Annotazione di dataset tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 Viene descritto come annotare lo schema XML Schema definition language (XSD) utilizzato per generare un oggetto fortemente tipizzato **DataSet**per assegnare **DataSet** nomi descrittivi di elementi senza alterare lo schema sottostante.  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
