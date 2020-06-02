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
ms.openlocfilehash: c8084cb8edff64b9d598f4fd0a62a362491c7aa7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281245"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Procedura: salvare fusi orari in una risorsa incorporata

Un'applicazione in grado di riconoscere il fuso orario richiede spesso la presenza di un determinato fuso orario. Tuttavia, poiché la disponibilità di singoli <xref:System.TimeZoneInfo> oggetti dipende dalle informazioni archiviate nel registro di sistema del sistema locale, anche i fusi orari disponibili abitualmente potrebbero essere assenti. Inoltre, le informazioni sui fusi orari personalizzati di cui è stata creata un'istanza tramite il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo non vengono archiviate con altre informazioni sul fuso orario nel registro di sistema. Per assicurarsi che questi fusi orari siano disponibili quando sono necessari, è possibile salvarli mediante la serializzazione e successivamente ripristinarli mediante la deserializzazione.

In genere, la serializzazione di un <xref:System.TimeZoneInfo> oggetto viene eseguita a parte l'applicazione in grado di riconoscere il fuso orario. A seconda dell'archivio dati utilizzato per contenere oggetti serializzati <xref:System.TimeZoneInfo> , i dati del fuso orario possono essere serializzati come parte di una routine di installazione o installazione, ad esempio quando i dati vengono archiviati in una chiave dell'applicazione del registro di sistema, o come parte di una routine di utilità eseguita prima che l'applicazione finale venga compilata, ad esempio quando i dati serializzati vengono archiviati in un file di risorse XML (con estensione resx) .NET.

Oltre a un file di risorse compilato con l'applicazione, è possibile usare diversi altri archivi dati per le informazioni sul fuso orario. tra cui:

- Registro di sistema. Si noti che un'applicazione deve usare le sottochiavi della propria chiave applicativa per archiviare i dati del fuso orario personalizzati anziché usare le sottochiavi di HKEY_LOCAL_MACHINE zone Nt\currentversion\time Zones di \SOFTWARE\Microsoft\Windows.

- File di configurazione.

- Altri file di sistema.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Per salvare un fuso orario eseguendo la serializzazione in un file con estensione resx

1. Recuperare un fuso orario esistente o creare un nuovo fuso orario.

   Per recuperare un fuso orario esistente, vedere [procedura: accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale](access-utc-and-local.md) e [procedura: creare un'istanza di un oggetto TimeZoneInfo](instantiate-time-zone-info.md).

   Per creare un nuovo fuso orario, chiamare uno degli overload del <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo. Per altre informazioni, vedere [procedura: creare fusi orari senza regole di rettifica](create-time-zones-without-adjustment-rules.md) e [procedura: creare fusi orari con regole di rettifica](create-time-zones-with-adjustment-rules.md).

2. Chiamare il <xref:System.TimeZoneInfo.ToSerializedString%2A> metodo per creare una stringa che contiene i dati del fuso orario.

3. Creare un'istanza <xref:System.IO.StreamWriter> di un oggetto fornendo il nome e, facoltativamente, il percorso del file con estensione resx al <xref:System.IO.StreamWriter> costruttore della classe.

4. Creare un'istanza <xref:System.Resources.ResXResourceWriter> di un oggetto passando l' <xref:System.IO.StreamWriter> oggetto al <xref:System.Resources.ResXResourceWriter> costruttore della classe.

5. Passare la stringa serializzata del fuso orario al <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> metodo.

6. Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> .

7. Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> .

8. Chiudere l' <xref:System.IO.StreamWriter> oggetto chiamando il relativo <xref:System.IO.StreamWriter.Close%2A> metodo.

9. Aggiungere il file resx generato al progetto di Visual Studio dell'applicazione.

10. Utilizzando la finestra **Proprietà** in Visual Studio, assicurarsi che la proprietà **azione di compilazione** del file. resx sia impostata su **risorsa incorporata**.

## <a name="example"></a>Esempio

Nell'esempio seguente viene serializzato un <xref:System.TimeZoneInfo> oggetto che rappresenta l'ora solare centrale e un <xref:System.TimeZoneInfo> oggetto che rappresenta la stazione di Palmer, l'ora antartica in un file di risorse XML .NET denominato SerializedTimeZones. resx. L'ora solare centrale è in genere definita nel registro di sistema; Palmer Station, Antartide è un fuso orario personalizzato.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

Questo esempio serializza <xref:System.TimeZoneInfo> gli oggetti in modo che siano disponibili in un file di risorse in fase di compilazione.

Poiché il <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> metodo aggiunge informazioni di intestazione complete a un file di risorse XML .NET, non può essere utilizzato per aggiungere risorse a un file esistente. L'esempio gestisce questa operazione controllando la presenza del file SerializedTimeZones. resx e, se esiste, archiviando tutte le relative risorse diverse dai due fusi orari serializzati in un <xref:System.Collections.Generic.Dictionary%602> oggetto generico. Il file esistente viene quindi eliminato e le risorse esistenti vengono aggiunte a un nuovo file SerializedTimeZones. resx. Anche i dati serializzati del fuso orario vengono aggiunti a questo file.

I campi chiave (o **nome**) delle risorse non devono contenere spazi incorporati. Il <xref:System.String.Replace%28System.String%2CSystem.String%29> metodo viene chiamato per rimuovere tutti gli spazi incorporati negli identificatori del fuso orario prima che vengano assegnati al file di risorse.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che un riferimento a System. Windows. Forms. dll e System. Core. dll venga aggiunto al progetto.

- Che vengano importati gli spazi dei nomi seguenti:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
- [Panoramica sul fuso orario](time-zone-overview.md)
- [Procedura: ripristinare i fusi orari da una risorsa incorporata](restore-time-zones-from-an-embedded-resource.md)
