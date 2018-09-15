---
title: 'Procedura: salvare fusi orari in una risorsa incorporata'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 921874e774d18751c29db495dac1bc53d10cc8ad
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2018
ms.locfileid: "45653347"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Procedura: salvare fusi orari in una risorsa incorporata

Una fuso orario dell'applicazione spesso richiede la presenza di un determinato fuso orario. Tuttavia, poiché la disponibilità dei singoli <xref:System.TimeZoneInfo> oggetti dipende dalle informazioni archiviate nel Registro di sistema locale, anche fusi orari generalmente disponibili può essere assente. Inoltre, viene creata un'istanza di informazioni sui fusi orari personalizzati usando il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> (metodo) non è archiviato con altre informazioni sul fuso orario nel Registro di sistema. Per garantire che i fusi orari disponibili quando sono necessari, è possibile salvarli serializzando li e ripristinarli in un secondo momento per la deserializzazione.

In genere, la serializzazione un <xref:System.TimeZoneInfo> oggetto presente a parte l'applicazione abilitata per il fuso orario. A seconda l'archivio dati usato per contenere serializzato <xref:System.TimeZoneInfo> oggetti, dati del fuso orario possono essere serializzati come parte di una routine di installazione o configurazione (ad esempio, quando i dati vengono archiviati in una chiave applicazione del Registro di sistema) o come parte di una routine di utilità che esegue prima che venga compilata l'applicazione finale (ad esempio, quando i dati serializzati vengono archiviati in un file di risorse (resx) XML di .NET).

Oltre a un file di risorse che viene compilato con l'applicazione, diversi altri archivi dati è utilizzabile per informazioni sul fuso orario. tra cui:

* Il Registro di sistema. Si noti che un'applicazione deve utilizzare le sottochiavi della chiave dell'applicazione per archiviare i dati di fuso orario personalizzato anziché utilizzare le sottochiavi della HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.

* File di configurazione.

* Altri file di sistema.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Per salvare un fuso orario per serializzarlo in un file resx

1. Recuperare un fuso orario esistente o creare un nuovo fuso orario.

   Per recuperare un fuso orario esistente, vedere [procedura: accedere ora UTC e l'ora locale zona agli oggetti predefiniti del](../../../docs/standard/datetime/access-utc-and-local.md) e [procedura: creare un'istanza di un oggetto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Per creare un nuovo fuso orario, chiamare uno degli overload del <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> (metodo). Per altre informazioni, vedere [procedura: creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) e [procedura: creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Chiamare il <xref:System.TimeZoneInfo.ToSerializedString%2A> metodo per creare una stringa che contiene i dati del fuso orario.

3. Creare un'istanza di un <xref:System.IO.StreamWriter> oggetto fornendo il nome e, facoltativamente, il percorso del file con estensione resx di <xref:System.IO.StreamWriter> costruttore della classe.

4. Creare un'istanza di un <xref:System.Resources.ResXResourceWriter> passando il <xref:System.IO.StreamWriter> dell'oggetto per il <xref:System.Resources.ResXResourceWriter> costruttore della classe.

5. Passare il fuso orario stringa serializzata al <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> (metodo).

6. Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Chiudi il <xref:System.IO.StreamWriter> chiamando il <xref:System.IO.StreamWriter.Close%2A> (metodo).

9. Aggiungere il file con estensione resx generati al progetto di Visual Studio dell'applicazione.

10. Usando il **proprietà** finestra in Visual Studio, assicurarsi che il file con estensione resx **azione di compilazione** viene impostata su **risorsa incorporata**.

## <a name="example"></a>Esempio

L'esempio seguente serializza un <xref:System.TimeZoneInfo> oggetto che rappresenta l'ora solare fuso centrale e un <xref:System.TimeZoneInfo> oggetto che rappresenta il Palmer Station, Antartide a un file di risorse .NET XML denominato SerializedTimeZones. Ora solare fuso centrale viene in genere definita nel Registro di sistema. Palmer Station, Antartide è un fuso orario personalizzato.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

In questo esempio serializza <xref:System.TimeZoneInfo> gli oggetti in modo che siano disponibili in un file di risorse in fase di compilazione.

Poiché il <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> metodo aggiunge informazioni di intestazione completa in un file di risorsa XML .NET, non può essere usato per aggiungere risorse a un file esistente. Nell'esempio viene gestita tramite il controllo dei file SerializedTimeZones e, se presente, l'archiviazione di tutte le relative risorse diverso da due fusi orari serializzati generico <xref:System.Collections.Generic.Dictionary%602> oggetto. Il file esistente viene eliminato e le risorse esistenti vengono aggiunti a un nuovo file SerializedTimeZones. I dati serializzati fuso orario viene inoltre aggiunto a questo file.

La chiave (o **nome**) i campi delle risorse non devono contenere spazi incorporati. Il <xref:System.String.Replace%28System.String%2CSystem.String%29> metodo viene chiamato per rimuovere tutti gli spazi incorporati negli identificatori del fuso orario, prima che vengano assegnati al file di risorse.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Aggiungere un riferimento alla DLL e Forms al progetto.

* Che siano importati spazi dei nomi seguenti:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vedere anche

* [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
* [Panoramica sui fusi orari](../../../docs/standard/datetime/time-zone-overview.md)
* [Procedura: Ripristinare i fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
