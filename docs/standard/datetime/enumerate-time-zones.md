---
title: 'Procedura: enumerare i fusi orari presenti in un computer'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
ms.openlocfilehash: 8f1cc9d58bc0f169d458854eac6568caaa4481c7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286132"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Procedura: enumerare i fusi orari presenti in un computer

Per poter usare correttamente un determinato fuso orario è necessario che nel sistema siano disponibili le informazioni sul fuso orario. I sistemi operativi Windows XP e Windows Vista archiviano queste informazioni nel registro di sistema. Sebbene nel mondo esistano molti fusi orari, le informazioni presenti nel Registro di sistema sono relative solo a una parte di essi. Inoltre, il Registro di sistema è una struttura dinamica il cui contenuto è soggetto a modifiche intenzionali e accidentali. Di conseguenza, un'applicazione non può sempre presupporre che un determinato fuso orario sia definito e disponibile in un sistema. Il primo passaggio per molte applicazioni che si basano sulle informazioni del fuso orario è determinare se i fusi orari richiesti sono disponibili nel sistema locale o offrire all'utente un elenco di fusi orari da selezionare. A tale scopo, è necessario che un'applicazione sia in grado di enumerare i fusi orari definiti in un sistema locale.

> [!NOTE]
> Se un'applicazione si basa sulla presenza di un determinato fuso orario che non può essere definito in un sistema locale, l'applicazione può garantirne la presenza mediante la serializzazione e la deserializzazione delle informazioni sul fuso orario. Il fuso orario può quindi essere aggiunto a un controllo elenco in modo che l'utente dell'applicazione possa selezionarlo. Per informazioni dettagliate, vedere [procedura: salvare fusi orari in una risorsa incorporata](save-time-zones-to-an-embedded-resource.md) e [procedura: ripristinare i fusi orari da una risorsa incorporata](restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Per enumerare i fusi orari presenti nel sistema locale

1. Chiamare il metodo <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> . Il metodo restituisce una raccolta generica <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> di <xref:System.TimeZoneInfo> oggetti. Le voci della raccolta sono ordinate in base alla relativa <xref:System.TimeZoneInfo.DisplayName%2A> Proprietà. Ad esempio:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Enumerare i singoli <xref:System.TimeZoneInfo> oggetti nella raccolta usando un `foreach` ciclo (in C#) o `For Each` ...`Next` loop (in Visual Basic) ed eseguire tutte le operazioni di elaborazione necessarie per ogni oggetto. Nel codice seguente, ad esempio, viene enumerata la <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> raccolta di <xref:System.TimeZoneInfo> oggetti restituiti nel passaggio 1 ed è elencato il nome visualizzato di ogni fuso orario nella console.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Per presentare all'utente un elenco di fusi orari presenti nel sistema locale

1. Chiamare il metodo <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> . Il metodo restituisce una raccolta generica <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> di <xref:System.TimeZoneInfo> oggetti.

2. Assegnare la raccolta restituita nel passaggio 1 alla `DataSource` proprietà di un controllo elenco di Windows Forms o ASP.NET.

3. Recuperare l' <xref:System.TimeZoneInfo> oggetto selezionato dall'utente.

Nell'esempio viene illustrata un'applicazione Windows.

## <a name="example"></a>Esempio

Nell'esempio viene avviata un'applicazione Windows che Visualizza i fusi orari definiti in un sistema in una casella di riepilogo. Viene quindi visualizzata una finestra di dialogo contenente il valore della <xref:System.TimeZoneInfo.DisplayName%2A> proprietà dell'oggetto fuso orario selezionato dall'utente.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

La maggior parte dei controlli elenco (ad esempio il <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> controllo o) consente di assegnare una raccolta di variabili oggetto alla relativa `DataSource` proprietà, purché tale raccolta implementi l' <xref:System.Collections.IEnumerable> interfaccia. Questa operazione viene eseguita dalla classe generica <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> . Per visualizzare un singolo oggetto nella raccolta, il controllo chiama il metodo dell'oggetto `ToString` per estrarre la stringa utilizzata per rappresentare l'oggetto. Nel caso degli <xref:System.TimeZoneInfo> oggetti, il `ToString` metodo restituisce il <xref:System.TimeZoneInfo> nome visualizzato dell'oggetto (il valore della relativa <xref:System.TimeZoneInfo.DisplayName%2A> proprietà).

> [!NOTE]
> Poiché i controlli elenco chiamano il metodo di un oggetto `ToString` , è possibile assegnare una raccolta di <xref:System.TimeZoneInfo> oggetti al controllo, fare in modo che il controllo visualizzi un nome significativo per ogni oggetto e recuperare l' <xref:System.TimeZoneInfo> oggetto selezionato dall'utente. In questo modo si elimina la necessità di estrarre una stringa per ogni oggetto della raccolta, assegnare la stringa a una raccolta a sua volta assegnata alla proprietà del controllo `DataSource` , recuperare la stringa selezionata dall'utente e quindi usare questa stringa per estrarre l'oggetto che descrive.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che vengano importati gli spazi dei nomi seguenti:

  <xref:System>(nel codice C#)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](index.md)
- [Procedura: salvare fusi orari in una risorsa incorporata](save-time-zones-to-an-embedded-resource.md)
- [Procedura: ripristinare i fusi orari da una risorsa incorporata](restore-time-zones-from-an-embedded-resource.md)
