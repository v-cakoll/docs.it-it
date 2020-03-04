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
ms.openlocfilehash: aa8962c8aea208778983610041937dc3f75c1f1e
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159442"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Procedura: enumerare i fusi orari presenti in un computer

Per poter usare correttamente un determinato fuso orario è necessario che nel sistema siano disponibili le informazioni sul fuso orario. I sistemi operativi Windows XP e Windows Vista archiviano queste informazioni nel registro di sistema. Sebbene nel mondo esistano molti fusi orari, le informazioni presenti nel Registro di sistema sono relative solo a una parte di essi. Inoltre, il Registro di sistema è una struttura dinamica il cui contenuto è soggetto a modifiche intenzionali e accidentali. Di conseguenza, un'applicazione non può sempre presupporre che un determinato fuso orario sia definito e disponibile in un sistema. Il primo passaggio per molte applicazioni che si basano sulle informazioni del fuso orario è determinare se i fusi orari richiesti sono disponibili nel sistema locale o offrire all'utente un elenco di fusi orari da selezionare. A tale scopo, è necessario che un'applicazione sia in grado di enumerare i fusi orari definiti in un sistema locale.

> [!NOTE]
> Se un'applicazione si basa sulla presenza di un determinato fuso orario che non può essere definito in un sistema locale, l'applicazione può garantirne la presenza mediante la serializzazione e la deserializzazione delle informazioni sul fuso orario. Il fuso orario può quindi essere aggiunto a un controllo elenco in modo che l'utente dell'applicazione possa selezionarlo. Per informazioni dettagliate, vedere [procedura: salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) e [procedura: ripristinare i fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Per enumerare i fusi orari presenti nel sistema locale

1. Chiamare il metodo <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> . Il metodo restituisce una raccolta di <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> generica di oggetti <xref:System.TimeZoneInfo>. Le voci della raccolta sono ordinate in base alla relativa proprietà <xref:System.TimeZoneInfo.DisplayName%2A>. Ad esempio:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Enumerare i singoli oggetti <xref:System.TimeZoneInfo> nella raccolta usando un ciclo di `foreach` (in C#) o un `For Each`...`Next` loop (in Visual Basic) ed eseguire tutte le operazioni di elaborazione necessarie per ogni oggetto. Il codice seguente, ad esempio, enumera il <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> raccolta di oggetti <xref:System.TimeZoneInfo> restituiti nel passaggio 1 ed elenca il nome visualizzato di ogni fuso orario nella console.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Per presentare all'utente un elenco di fusi orari presenti nel sistema locale

1. Chiamare il metodo <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> . Il metodo restituisce una raccolta di <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> generica di oggetti <xref:System.TimeZoneInfo>.

2. Assegnare la raccolta restituita nel passaggio 1 alla proprietà `DataSource` di un controllo elenco Windows Forms o ASP.NET.

3. Recuperare l'oggetto <xref:System.TimeZoneInfo> selezionato dall'utente.

Nell'esempio viene illustrata un'applicazione Windows.

## <a name="example"></a>Esempio

Nell'esempio viene avviata un'applicazione Windows che Visualizza i fusi orari definiti in un sistema in una casella di riepilogo. Viene quindi visualizzata una finestra di dialogo contenente il valore della proprietà <xref:System.TimeZoneInfo.DisplayName%2A> dell'oggetto fuso orario selezionato dall'utente.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

La maggior parte dei controlli elenco (ad esempio <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> o controllo <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType>) consente di assegnare una raccolta di variabili oggetto alla relativa proprietà `DataSource`, purché tale raccolta implementi l'interfaccia <xref:System.Collections.IEnumerable>. La classe generica <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> esegue questa operazione. Per visualizzare un singolo oggetto nella raccolta, il controllo chiama il metodo di `ToString` dell'oggetto per estrarre la stringa utilizzata per rappresentare l'oggetto. Nel caso di oggetti <xref:System.TimeZoneInfo>, il metodo `ToString` restituisce il nome visualizzato dell'oggetto <xref:System.TimeZoneInfo> (il valore della relativa proprietà <xref:System.TimeZoneInfo.DisplayName%2A>).

> [!NOTE]
> Poiché i controlli elenco chiamano il metodo `ToString` di un oggetto, è possibile assegnare una raccolta di oggetti <xref:System.TimeZoneInfo> al controllo, fare in modo che il controllo visualizzi un nome significativo per ogni oggetto e recuperare l'oggetto <xref:System.TimeZoneInfo> selezionato dall'utente. In questo modo si elimina la necessità di estrarre una stringa per ogni oggetto della raccolta, assegnare la stringa a una raccolta a sua volta assegnata alla proprietà `DataSource` del controllo, recuperare la stringa selezionata dall'utente e quindi usare questa stringa per estrarre l'oggetto che descrive.

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Che vengano importati gli spazi dei nomi seguenti:

  <xref:System> (in C# codice)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Procedura: Salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [Procedura: Ripristinare i fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
