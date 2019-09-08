---
title: Dataset tipizzati
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 7c8111e0e62a57b6745a5ea0387fc65a05839df8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785846"
---
# <a name="typed-datasets"></a>Dataset tipizzati
Oltre all'accesso ad associazione tardiva ai valori tramite variabili tipizzate in modo debole, nel tipo <xref:System.Data.DataSet> è disponibile l'accesso ai dati tramite una metafora tipizzata in modo sicuro. È possibile accedere alle tabelle e alle colonne che fanno parte del **set di dati** utilizzando nomi descrittivi e variabili fortemente tipizzate.  
  
 Un **DataSet** tipizzato è una classe che deriva da un **set di dati**. Di conseguenza, eredita tutti i metodi, gli eventi e le proprietà di un **set di dati**. Un **set di dati** tipizzato fornisce inoltre metodi, eventi e proprietà fortemente tipizzati. È quindi possibile accedere mediante il nome alle tabelle e alle colonne, invece di usare metodi basati sulle raccolte. Oltre alla migliore leggibilità del codice, un **set di dati** tipizzato consente anche all'editor di codice di Visual Studio .NET di completare automaticamente le righe durante la digitazione.  
  
 Il **set di dati** fortemente tipizzato fornisce inoltre l'accesso ai valori come tipo corretto in fase di compilazione. Con un set di **dati**fortemente tipizzato, vengono rilevati errori di mancata corrispondenza dei tipi quando il codice viene compilato anziché in fase di esecuzione.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Generazione di oggetti DataSet fortemente tipizzati](generating-strongly-typed-datasets.md)  
 Viene descritto come creare e utilizzare un set di **dati**fortemente tipizzato.  
  
 [Annotazione di oggetti DataSet tipizzati](annotating-typed-datasets.md)  
 Viene descritto come aggiungere annotazioni allo schema XSD (XML Schema Definition Language) utilizzato per generare un **DataSet**fortemente tipizzato, in modo da assegnare agli elementi del **set di dati** nomi descrittivi senza modificare lo schema sottostante.  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
