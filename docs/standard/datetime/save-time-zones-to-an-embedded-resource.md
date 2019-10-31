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
ms.openlocfilehash: aaee4e82d09e8b604d06dadb5a5eefe8d2e1f307
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123766"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Procedura: salvare fusi orari in una risorsa incorporata

Un'applicazione in grado di riconoscere il fuso orario richiede spesso la presenza di un determinato fuso orario. Tuttavia, poiché la disponibilità di singoli oggetti <xref:System.TimeZoneInfo> dipende dalle informazioni archiviate nel registro di sistema del sistema locale, anche i fusi orari disponibili abitualmente potrebbero essere assenti. Inoltre, le informazioni sui fusi orari personalizzati di cui è stata creata un'istanza tramite il metodo <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> non vengono archiviate con altre informazioni sul fuso orario nel registro di sistema. Per assicurarsi che questi fusi orari siano disponibili quando sono necessari, è possibile salvarli mediante la serializzazione e successivamente ripristinarli mediante la deserializzazione.

In genere, la serializzazione di un oggetto <xref:System.TimeZoneInfo> viene eseguita oltre all'applicazione in grado di riconoscere il fuso orario. A seconda dell'archivio dati utilizzato per contenere oggetti <xref:System.TimeZoneInfo> serializzati, i dati del fuso orario possono essere serializzati come parte di una routine di installazione o installazione (ad esempio, quando i dati vengono archiviati in una chiave dell'applicazione del registro di sistema) o come parte di una routine di utilità eseguita prima di l'applicazione finale viene compilata, ad esempio quando i dati serializzati vengono archiviati in un file di risorse XML (con estensione resx) .NET.

Oltre a un file di risorse compilato con l'applicazione, è possibile usare diversi altri archivi dati per le informazioni sul fuso orario. tra cui:

- Registro di sistema. Si noti che un'applicazione deve usare le sottochiavi della propria chiave applicativa per archiviare i dati del fuso orario personalizzati anziché usare le sottochiavi di HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Nt\currentversion\time Zones zone.

- File di configurazione.

- Altri file di sistema.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Per salvare un fuso orario eseguendo la serializzazione in un file con estensione resx

1. Recuperare un fuso orario esistente o creare un nuovo fuso orario.

   Per recuperare un fuso orario esistente, vedere [procedura: accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale](../../../docs/standard/datetime/access-utc-and-local.md) e [procedura: creare un'istanza di un oggetto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Per creare un nuovo fuso orario, chiamare uno degli overload del metodo <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>. Per altre informazioni, vedere [procedura: creare fusi orari senza regole di rettifica](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) e [procedura: creare fusi orari con regole di rettifica](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Chiamare il metodo <xref:System.TimeZoneInfo.ToSerializedString%2A> per creare una stringa che contiene i dati del fuso orario.

3. Creare un'istanza di un oggetto <xref:System.IO.StreamWriter> fornendo il nome e, facoltativamente, il percorso del file con estensione resx al costruttore della classe <xref:System.IO.StreamWriter>.

4. Creare un'istanza di un oggetto <xref:System.Resources.ResXResourceWriter> passando l'oggetto <xref:System.IO.StreamWriter> al costruttore della classe <xref:System.Resources.ResXResourceWriter>.

5. Passare la stringa serializzata del fuso orario al metodo <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType>.

6. Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Chiudere l'oggetto <xref:System.IO.StreamWriter> chiamando il relativo metodo <xref:System.IO.StreamWriter.Close%2A>.

9. Aggiungere il file resx generato al progetto di Visual Studio dell'applicazione.

10. Utilizzando la finestra **Proprietà** in Visual Studio, assicurarsi che la proprietà **azione di compilazione** del file. resx sia impostata su **risorsa incorporata**.

## <a name="example"></a>Esempio

Nell'esempio seguente viene serializzato un oggetto <xref:System.TimeZoneInfo> che rappresenta l'ora solare centrale e un oggetto <xref:System.TimeZoneInfo> che rappresenta l'ora di Palmer Station, Antartide in un file di risorse XML .NET denominato SerializedTimeZones. resx. L'ora solare centrale è in genere definita nel registro di sistema; Palmer Station, Antartide è un fuso orario personalizzato.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

Questo esempio serializza gli oggetti <xref:System.TimeZoneInfo> in modo che siano disponibili in un file di risorse in fase di compilazione.

Poiché il metodo <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> aggiunge informazioni di intestazione complete a un file di risorse XML .NET, non può essere utilizzato per aggiungere risorse a un file esistente. L'esempio gestisce questa operazione controllando la presenza del file SerializedTimeZones. resx e, se esiste, archiviando tutte le relative risorse diverse dai due fusi orari serializzati in un oggetto <xref:System.Collections.Generic.Dictionary%602> generico. Il file esistente viene quindi eliminato e le risorse esistenti vengono aggiunte a un nuovo file SerializedTimeZones. resx. Anche i dati serializzati del fuso orario vengono aggiunti a questo file.

I campi chiave (o **nome**) delle risorse non devono contenere spazi incorporati. Il metodo <xref:System.String.Replace%28System.String%2CSystem.String%29> viene chiamato per rimuovere tutti gli spazi incorporati negli identificatori del fuso orario prima che vengano assegnati al file di risorse.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che un riferimento a System. Windows. Forms. dll e System. Core. dll venga aggiunto al progetto.

- Che vengano importati gli spazi dei nomi seguenti:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Panoramica sui fusi orari](../../../docs/standard/datetime/time-zone-overview.md)
- [Procedura: Ripristinare i fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
