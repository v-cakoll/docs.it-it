---
title: Suggerimenti per lo sviluppo di applicazioni internazionali
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- global applications, best practices
- world-ready applications, best practices
- globalization [.NET Framework], best practices
- international applications [.NET Framework], best practices
ms.assetid: f08169c7-aad8-4ec3-9a21-9ebd3b89986c
ms.openlocfilehash: a2cd1039f95a763002922fc2fa24eff77838de80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141289"
---
# <a name="best-practices-for-developing-world-ready-applications"></a>Procedure consigliate per lo sviluppo di applicazioni internazionali

In questa sezione vengono forniti alcuni suggerimenti da seguire per lo sviluppo di applicazioni internazionali.

## <a name="globalization-best-practices"></a>Procedure consigliate per la globalizzazione

1. Fare in modo che l’applicazione si basi internamente sulla codifica Unicode.

2. Utilizzare classi con il supporto delle impostazioni cultura fornite dallo spazio dei nomi <xref:System.Globalization> per modificare e formattare i dati.

    - Per l'ordinamento, utilizzare le classi <xref:System.Globalization.SortKey> e <xref:System.Globalization.CompareInfo>.

    - Per i confronti di stringhe, utilizzare la classe <xref:System.Globalization.CompareInfo>.

    - Per la formattazione di data e ora, utilizzare la classe <xref:System.Globalization.DateTimeFormatInfo>.

    - Per la formattazione dei numeri, utilizzare la classe <xref:System.Globalization.NumberFormatInfo>.

    - Per i calendari gregoriano e non gregoriano, utilizzare la classe <xref:System.Globalization.Calendar> o una delle implementazioni specifiche del calendario.

3. Utilizzare le impostazioni delle proprietà relative alle impostazioni cultura fornite dalla classe <xref:System.Globalization.CultureInfo?displayProperty=nameWithType> nelle situazioni appropriate. Utilizzare la proprietà <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> per le attività di formattazione, ad esempio per la formattazione della data e dell'ora o dei numeri. Utilizzare la proprietà <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> per recuperare le risorse. Si noti che le proprietà `CurrentCulture` e `CurrentUICulture` possono essere impostate per ogni thread.

4. Impostare l'applicazione in modo da consentire la lettura e scrittura di dati da e verso una vasta gamma di codifiche, utilizzando le classi di codifica nello spazio dei nomi <xref:System.Text>. Non utilizzare dati ASCII. Partire dal presupposto che verranno forniti caratteri internazionali in qualsiasi punto in cui un utente può immettere testo. L'applicazione deve, ad esempio, accettare i caratteri internazionali in nomi di server, directory, nomi file, nomi utente e URL.

5. Quando si utilizza la classe <xref:System.Text.UTF8Encoding>, per motivi di sicurezza utilizzare la funzionalità di rilevamento degli errori offerta da questa classe. Per attivare la funzionalità di rilevamento degli errori, creare un'istanza della classe usando il costruttore che accetta un parametro `throwOnInvalidBytes` e impostare il valore di questo parametro su `true`.

6. Quando possibile, gestire le stringhe come unità intere e non come serie di caratteri singoli. Questo metodo di gestione è particolarmente importante quando si ordinano o si cercano sottostringhe. In questo modo non si verificheranno problemi associati all'analisi dei caratteri combinati. È anche possibile operare con unità di testo invece che con caratteri singoli usando la classe <xref:System.Globalization.StringInfo?displayProperty=nameWithType>.

7. Visualizzare il testo utilizzando le classi fornite dallo spazio dei nomi <xref:System.Drawing>.

8. Per garantire l'uniformità tra i sistemi operativi, non consentire l'override di <xref:System.Globalization.CultureInfo> da parte delle impostazioni utente. Utilizzare il costruttore di `CultureInfo` che accetta un parametro `useUserOverride` e impostarlo su `false`.

9. Eseguire il test della funzionalità dell'applicazione in versioni internazionali dei sistemi operativi utilizzando dati internazionali.

10. Se una decisione relativa alla sicurezza è basata sul risultato di un confronto di stringhe o di un'operazione di modifica delle lettere maiuscole e minuscole, usare un'operazione stringa indipendente dalle impostazioni cultura. In questo modo è possibile verificare che il valore di `CultureInfo.CurrentCulture` non influisca sul risultato. Vedere la sezione "Confronti di stringhe che utilizzano le impostazioni [cultura correnti"](../../../docs/standard/base-types/best-practices-strings.md#string-comparisons-that-use-the-current-culture) di procedure consigliate per l'utilizzo di [stringhe](../../../docs/standard/base-types/best-practices-strings.md) per un esempio che illustra come i confronti tra stringhe dipendenti dalle impostazioni cultura possono produrre risultati incoerenti.

## <a name="localization-best-practices"></a>Procedure consigliate per la localizzazione

1. Spostare tutte le risorse localizzabili in DLL distinte di sole risorse. Le risorse localizzabili includono gli elementi dell'interfaccia utente quali stringhe, messaggi di errore, finestre di dialogo, menu e risorse di oggetti incorporati.

2. Non impostare stringhe o risorse dell'interfaccia utente come hardcoded.

3. Non collocare le risorse non localizzabili nelle DLL di sole risorse, per evitare di creare confusione ai traduttori.

4. Non utilizzate stringhe composte che sono compilate in fase di esecuzione da frasi concatenate. Le stringhe composte sono difficili da localizzare, in quanto richiedono spesso un ordine grammaticale in inglese che non è valido per tutte le lingue.

5. Evitare costrutti ambigui, come ad esempio "Empty Folder" in cui le stringhe possono essere tradotte in modo diverso in base alle regole grammaticali dei componenti stringa. La stringa "empty", ad esempio, può essere un verbo o un aggettivo e può essere tradotta in modo diverso in alcune lingue, come ad esempio l'italiano o il francese.

6. Evitare l'utilizzo di immagini e icone contenenti testo all'interno dell'applicazione, in quanto sono costose da localizzare.

7. Lasciare sufficiente spazio vuoto per consentire l'espansione della lunghezza delle stringhe nell'interfaccia utente. In alcune lingue le frasi possono richiedere il 50-75% di spazio in più rispetto ad altre lingue.

8. Utilizzare la classe <xref:System.Resources.ResourceManager?displayProperty=nameWithType> per recuperare le risorse in base alle impostazioni cultura.

9. Usare [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) per creare finestre di dialogo Windows Form in modo che possano essere localizzate tramite l'[Editor risorse di Windows Form (Winres.exe)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md). Non codificare manualmente le finestre di dialogo di Windows Form.

10. Assegnare la localizzazione (traduzione) a professionisti.

11. Per una descrizione completa della creazione e localizzazione delle risorse, vedere [Risorse nelle applicazioni](../../../docs/framework/resources/index.md).

## <a name="globalization-best-practices-for-aspnet-applications"></a>Procedure consigliate per la globalizzazione per le applicazioni ASP.NET

1. Impostare in modo esplicito le proprietà <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> e <xref:System.Globalization.CultureInfo.CurrentCulture%2A> nell'applicazione in uso. Non utilizzare i valori predefiniti.

2. Si noti che le applicazioni ASP.NET sono applicazioni gestite e possono utilizzare le stesse classi delle altre applicazioni gestite per il recupero, la visualizzazione e la manipolazione delle informazioni in base alle impostazioni cultura.

3. Tenere presente che in ASP.NET è possibile specificare i tre tipi di codifiche descritti di seguito.

    - requestEncoding: specifica la codifica ricevuta dal browser del client.

    - responseEncoding: specifica la codifica da inviare al browser del client. Nella maggior parte dei casi questa codifica deve corrispondere a quella specificata per requestEncoding.

    - fileEncoding: specifica la codifica predefinita per l'analisi dei file con estensione aspx, asmx e asax.

4. Specificare i valori per gli attributi requestEncoding, responseEncoding, fileEncoding, culture e uiCulture nei seguenti tre punti in un'applicazione ASP.NET:

    - Nella sezione di globalizzazione di un file Web.config. Questo file è esterno all'applicazione ASP.NET. Per ulteriori informazioni, vedere [ \<globalizzazione> Element](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hy4kkhe0(v=vs.100)).

    - In un'istruzione di pagina. Si noti che quando in un'applicazione viene visualizzata una pagina, il file è già stato letto, pertanto non è più possibile specificare fileEncoding e requestEncoding. In un'istruzione di pagina è possibile specificare solo uiCulture, Culture e responseEncoding.

    - A livello di codice, nel codice dell'applicazione. Questa impostazione può variare in base alla richiesta. Come con un'istruzione di pagina, raggiunto il codice dell'applicazione non è più possibile specificare fileEncoding e requestEncoding. Nel codice dell'applicazione è possibile specificare solo uiCulture, Culture e responseEncoding.

5. Si noti che il valore di uiCulture può essere impostato sulla lingua del browser.

## <a name="see-also"></a>Vedere anche

- [Globalizzazione e localizzazione](../../../docs/standard/globalization-localization/index.md)
- [Risorse nelle applicazioni desktop](../../../docs/framework/resources/index.md)
