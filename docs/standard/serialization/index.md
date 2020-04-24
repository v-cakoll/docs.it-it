---
title: Serializzazione-.NET
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: e6db24326c79ab6509b253c45c27f87a2aacd73c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053353"
---
# <a name="serialization-in-net"></a>Serializzazione in .NET

La serializzazione è il processo di conversione dello stato di un oggetto in un form che può essere mantenuto o trasportato. Il complemento della serializzazione è la deserializzazione, che converte un flusso in un oggetto. Insieme, questi processi consentono di archiviare e trasferire i dati.  
  
.NET offre le seguenti tecnologie di serializzazione:  
  
- La [serializzazione binaria](binary-serialization.md) consente di mantenere la fedeltà dei tipi, utile per mantenere lo stato di un oggetto tra chiamate diverse di un'applicazione. È possibile, ad esempio, condividere un oggetto tra diverse applicazioni serializzandolo negli Appunti. La serializzazione di un oggetto può essere effettuata in un flusso, in un disco, in memoria, in rete e così via. .NET Remoting utilizza la serializzazione per passare oggetti "per valore" da un computer o dominio dell'applicazione a un altro.  
  
- La [serializzazione SOAP e XML](xml-and-soap-serialization.md) serializza solo i campi e le proprietà pubbliche e non mantiene la fedeltà del tipo. Ciò risulta utile se si vuole fornire o utilizzare dati senza limitare l'applicazione che utilizza i dati. Poiché XML è uno standard aperto, questa rappresenta una scelta interessante ai fini della condivisione di dati attraverso il Web. Analogamente, SOAP è uno standard aperto che rappresenta una scelta altrettanto interessante.  
  
- La [serializzazione JSON](system-text-json-overview.md) serializza solo le proprietà pubbliche e non mantiene la fedeltà del tipo. JSON è uno standard aperto che rappresenta una scelta interessante per la condivisione di dati sul Web.

## <a name="reference"></a>Informazioni di riferimento

<xref:System.Runtime.Serialization>  
Contiene classi utilizzabili per la serializzazione e la deserializzazione di oggetti.
  
<xref:System.Xml.Serialization>  
Contiene classi utilizzabili per la serializzazione di oggetti in documenti XML o in flussi.

<xref:System.Text.Json>  
Contiene classi che possono essere usate per serializzare oggetti in flussi o documenti in formato JSON.
