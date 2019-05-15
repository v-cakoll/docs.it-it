---
title: Serializzazione in .NET
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 1f90a128ef6b29acbd315beae7aaaf1d1b78a62b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638853"
---
# <a name="serialization-in-net"></a>Serializzazione in .NET
La serializzazione è il processo di conversione dello stato di un oggetto in un form che può essere mantenuto o trasportato. Il complemento della serializzazione è la deserializzazione, che converte un flusso in un oggetto. Insieme, questi processi consentono di archiviare e trasferire i dati in modo semplice.  
  
.NET offre due tecnologie di serializzazione:  
  
- La serializzazione binaria mantiene la fedeltà dei tipi, utile per il mantenimento dello stato di un oggetto tra chiamate diverse di un'applicazione. È possibile, ad esempio, condividere un oggetto tra diverse applicazioni serializzandolo negli Appunti. La serializzazione di un oggetto può essere effettuata in un flusso, in un disco, in memoria, in rete e così via. .NET Remoting utilizza la serializzazione per passare oggetti "per valore" da un computer o dominio dell'applicazione a un altro.  
  
- La serializzazione XML serializza solo i campi e le proprietà pubbliche e non mantiene la fedeltà dei tipi. Ciò risulta utile se si vuole fornire o utilizzare dati senza limitare l'applicazione che utilizza i dati. Poiché XML è uno standard aperto, questa rappresenta una scelta interessante ai fini della condivisione di dati attraverso il Web. Analogamente, SOAP è uno standard aperto che rappresenta una scelta altrettanto interessante.  
  
## <a name="in-this-section"></a>In questa sezione  
[Argomenti sulle procedure relative alla serializzazione](../../../docs/standard/serialization/serialization-how-to-topics.md)  
Vengono riportati collegamenti alle procedure contenute in questa sezione.
  
[Serializzazione binaria](../../../docs/standard/serialization/binary-serialization.md)  
Descrive il meccanismo della serializzazione binaria incluso nel Common Language Runtime.

[Serializzazione SOAP e XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
Descrive il meccanismo della serializzazione XML e SOAP incluso nel Common Language Runtime.

[Strumenti per la serializzazione](../../../docs/standard/serialization/serialization-tools.md)  
Questi strumenti consentono di sviluppare codice di serializzazione.

[Esempi di serializzazione](../../../docs/standard/serialization/serialization-samples.md)  
Negli esempi viene illustrato come eseguire la serializzazione.

## <a name="reference"></a>Riferimenti
<xref:System.Runtime.Serialization> Contiene classi che possono essere usate per la serializzazione e la deserializzazione di oggetti.
  
<xref:System.Xml.Serialization>  
Contiene classi utilizzabili per la serializzazione di oggetti in documenti XML o in flussi.
