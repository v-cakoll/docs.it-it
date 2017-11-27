---
title: 'Procedura: salvare fusi orari per una risorsa incorporata'
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96dd3f0a3ed27a9e09c62f3ad4f450ced5a8e644
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Procedura: salvare fusi orari per una risorsa incorporata

Un'applicazione di fuso orario spesso richiede la presenza di un particolare fuso orario. Tuttavia, poiché la disponibilità dei singoli <xref:System.TimeZoneInfo> oggetti dipende dalle informazioni archiviate nel Registro di sistema locale, anche fusi orari generalmente disponibili potrebbe essere assente. Inoltre, viene creata un'istanza di informazioni sui fusi orari personalizzati utilizzando il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> (metodo) non è archiviata con altre informazioni sul fuso orario nel Registro di sistema. Per assicurarsi che questi fusi orari disponibili quando sono necessari, è possibile salvarli serializzando li e ripristinarli in un secondo momento deserializzando li.

In genere, la serializzazione di un <xref:System.TimeZoneInfo> oggetto si verifica a parte l'applicazione di fuso orario. In base all'archivio dati utilizzato per contenere serializzato <xref:System.TimeZoneInfo> oggetti, dati del fuso orario possono essere serializzati come parte di una routine di installazione (ad esempio, quando i dati vengono archiviati in una chiave del Registro di sistema di applicazione) o come parte di una routine di utilità che viene eseguito prima di (ad esempio, quando i dati serializzati vengono archiviati in un file di risorse (resx) XML .NET), viene compilata l'applicazione finale.

Oltre a un file di risorse che viene compilato con l'applicazione, è possono utilizzare molti altri archivi dati per informazioni sul fuso orario. tra cui:

* Il Registro di sistema. Si noti che un'applicazione deve utilizzare le sottochiavi della chiave di applicazione per archiviare i dati del fuso orario personalizzato anziché il sottochiavi di HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.

* File di configurazione.

* Altri file di sistema.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Per salvare un fuso orario per la serializzazione, in un file con estensione resx

1. Recuperare un fuso orario esistente o creare un nuovo fuso orario.

   Per recuperare un fuso orario esistente, vedere [procedura: accedere oggetti fuso UTC e l'ora locali predefiniti](../../../docs/standard/datetime/access-utc-and-local.md) e [procedura: creare un'istanza di un oggetto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Per creare un nuovo fuso orario, chiamare uno degli overload di <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo. Per ulteriori informazioni, vedere [procedura: creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) e [procedura: creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Chiamare il <xref:System.TimeZoneInfo.ToSerializedString%2A> metodo per creare una stringa che contiene i dati del fuso orario.

3. Creare un'istanza di un <xref:System.IO.StreamWriter> fornendo il nome e, facoltativamente, il percorso del file con estensione resx il <xref:System.IO.StreamWriter> costruttore della classe.

4. Creare un'istanza di un <xref:System.Resources.ResXResourceWriter> oggetto passando il <xref:System.IO.StreamWriter> dell'oggetto per il <xref:System.Resources.ResXResourceWriter> costruttore della classe.

5. Passare il fuso orario stringa serializzata per il <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> metodo.

6. Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Chiudi il <xref:System.IO.StreamWriter> oggetto chiamando il relativo <xref:System.IO.StreamWriter.Close%2A> metodo.

9. Aggiungere il file con estensione resx generato al progetto di Visual Studio dell'applicazione.

10. Utilizzando il **proprietà** finestra in Visual Studio, assicurarsi che il file. resx **azione di compilazione** è impostata su **risorsa incorporata**.

## <a name="example"></a>Esempio

Nell'esempio seguente viene serializzata una <xref:System.TimeZoneInfo> oggetto che rappresenta l'ora solare fuso centrale e un <xref:System.TimeZoneInfo> oggetto che rappresenta la stazione Palmer, Antartide a un file di risorse XML .NET denominato SerializedTimeZones. Ora solare fuso centrale è in genere definito nel Registro di sistema. Palmer stazione, Antartide è un fuso orario personalizzato.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

In questo esempio serializza <xref:System.TimeZoneInfo> oggetti in modo che siano disponibili in un file di risorse in fase di compilazione.

Poiché il <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> metodo aggiunge informazioni di intestazione completa in un file di risorse XML .NET, e non può essere utilizzato per aggiungere risorse a un file esistente. Nell'esempio viene gestita mediante il controllo per il file SerializedTimeZones e, se presente, archiviando tutte le relative risorse eccetto i due fusi orari serializzati in un oggetto generico <xref:System.Collections.Generic.Dictionary%602> oggetto. Il file esistente viene eliminato e le risorse esistenti vengono aggiunti a un nuovo file SerializedTimeZones. I dati serializzati fuso orario viene anche aggiunto a questo file.

La chiave (o **nome**) i campi delle risorse non devono contenere spazi. Il <xref:System.String.Replace%28System.String%2CSystem.String%29> metodo viene chiamato per rimuovere tutti gli spazi negli identificatori del fuso orario prima che vengano assegnati al file di risorse.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Un riferimento a System.Core.dll e di Forms essere aggiunto al progetto.

* Che importati spazi dei nomi seguenti:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vedere anche

[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md)
[procedura: ripristinare fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
