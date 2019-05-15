---
title: 'Procedura: Enumerare i fusi orari presenti in un computer'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82898e80f5acb2cb0dcab65390701efc8d48115b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586568"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Procedura: Enumerare i fusi orari presenti in un computer

Per poter usare correttamente un determinato fuso orario è necessario che nel sistema siano disponibili le informazioni sul fuso orario. I sistemi operativi Windows XP e Windows Vista archiviare queste informazioni nel Registro di sistema. Sebbene nel mondo esistano molti fusi orari, le informazioni presenti nel Registro di sistema sono relative solo a una parte di essi. Inoltre, il Registro di sistema è una struttura dinamica il cui contenuto è soggetto a modifiche intenzionali e accidentali. Di conseguenza, un'applicazione non può sempre presupporre che un determinato fuso orario sia definito e disponibile in un sistema. Il primo passaggio per molte applicazioni che si basano sulle informazioni del fuso orario è determinare se i fusi orari richiesti sono disponibili nel sistema locale o offrire all'utente un elenco di fusi orari da selezionare. A tale scopo, è necessario che un'applicazione sia in grado di enumerare i fusi orari definiti in un sistema locale.

> [!NOTE]
> Se un'applicazione si basa sulla presenza di un determinato fuso orario che non può essere definita in un sistema locale, l'applicazione può garantire la sua presenza per la serializzazione e deserializzazione delle informazioni sul fuso orario. Il fuso orario può quindi essere aggiunto a un controllo elenco, in modo che l'utente dell'applicazione possa selezionarlo. Per informazioni dettagliate, vedere [Procedura: Salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) e [come: Ripristinare i fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Per enumerare i fusi orari presenti nel sistema locale

1. Chiamare il metodo <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. Il metodo restituisce un oggetto generico <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> raccolta di <xref:System.TimeZoneInfo> oggetti. Le voci nella raccolta vengono ordinati in base i <xref:System.TimeZoneInfo.DisplayName%2A> proprietà. Ad esempio:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Enumerare i singoli <xref:System.TimeZoneInfo> oggetti nella raccolta utilizzando una `foreach` ciclo (in c#) o un `For Each`...`Next` ciclo (in Visual Basic) ed eseguire tutte le elaborazioni necessarie su ogni oggetto. Ad esempio, il codice seguente enumera le <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> raccolta di <xref:System.TimeZoneInfo> oggetti restituiti nel passaggio 1 ed elenca il nome visualizzato di ogni fuso orario nella console.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Per presentare all'utente un elenco di fusi orari presenti nel sistema locale

1. Chiamare il metodo <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. Il metodo restituisce un oggetto generico <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> raccolta di <xref:System.TimeZoneInfo> oggetti.

2. Assegnare l'insieme restituito nel passaggio 1 per il `DataSource` proprietà di un Windows Form o ASP.NET controllo elenco.

3. Recuperare il <xref:System.TimeZoneInfo> oggetto che l'utente ha selezionato.

Nell'esempio viene fornita un'illustrazione di un'applicazione Windows.

## <a name="example"></a>Esempio

L'esempio avvia un'applicazione Windows che consente di visualizzare i fusi orari definiti in un sistema in una casella di riepilogo. Nell'esempio viene quindi visualizza una finestra di dialogo che contiene il valore della <xref:System.TimeZoneInfo.DisplayName%2A> proprietà dell'oggetto fuso orario selezionato dall'utente.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

Più controlli di elenco (come il <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> o <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> controllo) consentono di assegnare una raccolta di variabili oggetto per loro `DataSource` proprietà fino a quando tale raccolta implementa il <xref:System.Collections.IEnumerable> interfaccia. (Il tipo generico <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> eseguita dalla classe.) Per visualizzare un singolo oggetto nella raccolta, il controllo chiama tale oggetto `ToString` metodo per estrarre la stringa utilizzata per rappresentare l'oggetto. Nel caso di <xref:System.TimeZoneInfo> oggetti, il `ToString` metodo restituisce il <xref:System.TimeZoneInfo> nome visualizzato dell'oggetto (il valore della relativa <xref:System.TimeZoneInfo.DisplayName%2A> proprietà).

> [!NOTE]
> Poiché i controlli elenco chiamano un oggetto `ToString` metodo, è possibile assegnare una raccolta di <xref:System.TimeZoneInfo> gli oggetti per il controllo, che il controllo Visualizza un nome significativo per ogni oggetto e recuperare il <xref:System.TimeZoneInfo> oggetto che l'utente ha selezionato. Ciò elimina la necessità di estrarre una stringa per ogni oggetto nella raccolta, la stringa assegnata a una raccolta che a sua volta viene assegnata al controllo `DataSource` proprietà, recuperare la stringa di cui l'utente ha selezionato e quindi usare questa stringa per estrarre l'oggetto da descrivere. 

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

* Che siano importati spazi dei nomi seguenti:

  <xref:System> (in codice c#)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Vedere anche

- [Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
- [Procedura: Salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [Procedura: Ripristinare i fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
