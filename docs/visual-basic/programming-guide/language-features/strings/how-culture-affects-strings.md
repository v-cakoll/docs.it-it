---
title: Influenza delle impostazioni cultura sulle stringhe in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
ms.openlocfilehash: d3c7ae9da9c18e53da393928e34dcfbf04fc891c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834621"
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Influenza delle impostazioni cultura sulle stringhe in Visual Basic
Questa pagina della Guida viene illustrato come Visual Basic Usa informazioni sulle impostazioni cultura per eseguire confronti e le conversioni di stringa.  
  
## <a name="when-to-use-culture-specific-strings"></a>Quando usare stringhe specifiche delle impostazioni cultura  
 In genere, si dovrebbe usare stringhe specifiche delle impostazioni cultura per tutti i dati presentati lettura dagli utenti e usare stringhe indipendente dalle impostazioni cultura per i dati dell'applicazione interna.  
  
 Ad esempio, se l'applicazione chiede agli utenti di immettere una data come stringa, deve aspettarsi che gli utenti per formattare le stringhe in base alla loro delle impostazioni cultura e l'applicazione deve convertire la stringa in modo appropriato. Se l'applicazione presenta quindi tale data nell'interfaccia utente, deve presentarla nelle impostazioni cultura dell'utente.  
  
 Tuttavia, se l'applicazione carica la data in un server centrale, deve formattare la stringa in base a una lingua specifica, per evitare confusione tra formati di data potenzialmente diversi.  
  
## <a name="culture-sensitive-functions"></a>Funzioni dipendenti dalle impostazioni cultura  
 Tutte le funzioni di conversione di stringhe Visual Basic (tranne che per il `Str` e `Val` funzioni) usare le informazioni dell'applicazione delle impostazioni cultura per assicurarsi che le conversioni e i confronti siano appropriati per le impostazioni cultura dell'applicazione utente.  
  
 La chiave per l'utilizzo corretto delle funzioni di conversione di stringhe nelle applicazioni eseguite in computer con diverse impostazioni cultura consiste nel comprendere le funzioni che usano impostazioni cultura specifiche e che utilizzano le impostazioni cultura correnti. Si noti che le impostazioni dell'applicazione delle impostazioni cultura sono, per impostazione predefinita, ereditate dalle impostazioni cultura del sistema operativo. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, e [CString](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Il `Str` (converte i numeri in stringhe) e `Val` funzioni (conversione di stringhe in numeri) non utilizzano informazioni sulle impostazioni cultura dell'applicazione durante la conversione tra stringhe e numeri. Al contrario, si riconosce solo il punto (.) come separatore dei decimale valido. Le soluzioni analoghe disponibili sensibili di queste funzioni sono:  
  
-   **Conversioni per cui le impostazioni cultura correnti.** Il `CStr` e `Format` funzioni convertono una stringa, un numero e il `CDbl` e `CInt` funzioni convertono una stringa in un numero.  
  
-   **Conversioni che usano impostazioni cultura specifiche.** Ogni oggetto number presenta una `ToString(IFormatProvider)` metodo che converte un numero in una stringa, e un `Parse(String, IFormatProvider)` metodo che converte una stringa in un numero. Ad esempio, il `Double` tipo fornisce il <xref:System.Double.ToString%28System.IFormatProvider%29> e <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> metodi.  
  
 Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Conversion.Str%2A> e <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## <a name="using-a-specific-culture"></a>Usando impostazioni cultura  
 Si supponga che si sta sviluppando un'applicazione che invia una data (formattata sotto forma di stringa) a un servizio Web. In questo caso, l'applicazione deve usare impostazioni cultura specifiche per la conversione di stringa. Per illustrare il motivo, considerare i risultati ottenuti utilizzando la data <xref:System.DateTime.ToString> metodo: Se l'applicazione usa questo metodo per formattare la data 4 luglio 2005, viene restituito "7/4/2005 12:00:00 AM" viene eseguito con impostazioni cultura inglese Stati Uniti (en-US), ma restituisce "04.07.2005 00:00:00" viene eseguito con le impostazioni cultura tedesco (de-DE).  
  
 Quando è necessario eseguire una conversione di stringhe in un formato specifico delle impostazioni cultura, è consigliabile usare la `CultureInfo` classe che viene compilato nel [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. È possibile creare una nuova `CultureInfo` oggetto delle impostazioni cultura, passando il nome delle impostazioni cultura per il <xref:System.Globalization.CultureInfo.%23ctor%2A> costruttore. I nomi di impostazioni cultura supportate sono elencati nel <xref:System.Globalization.CultureInfo> pagina della Guida di classe.  
  
 In alternativa, è possibile ottenere un'istanza del *invariabile* dal <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> proprietà. La lingua inglese è basata sulla lingua inglese, ma esistono alcune differenze. Le impostazioni cultura invarianti ad esempio, specificano un orologio di 24 ore invece di un formato a 12 ore.  
  
 Per convertire una data nella stringa delle impostazioni cultura, passare il <xref:System.Globalization.CultureInfo> oggetto dell'oggetto data <xref:System.DateTime.ToString%28System.IFormatProvider%29> (metodo). Ad esempio, il codice seguente consente di visualizzare "04/07/2005 00:00:00", indipendentemente dalle impostazioni cultura dell'applicazione.  
  
 [!code-vb[VbVbalrConcepts#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#1)]  
  
> [!NOTE]
>  Valori letterali data vengono sempre interpretati in base alle impostazioni cultura inglesi.  
  
## <a name="comparing-strings"></a>Confronto di stringhe  
 Esistono due importanti situazioni in cui sono necessari i confronti di stringhe:  
  
-   **L'ordinamento dei dati da visualizzare all'utente.** Usare le operazioni in base alla lingua corrente in modo che le stringhe di ordinamento in modo appropriato.  
  
-   **Determinare se due stringhe dell'applicazione interna corrispondono esattamente (in genere per motivi di sicurezza).** Usare le operazioni che non tengono conto delle impostazioni cultura correnti.  
  
 È possibile eseguire entrambi i tipi di confronti con Visual Basic <xref:Microsoft.VisualBasic.Strings.StrComp%2A> (funzione). Specificare l'opzione facoltativa `Compare` argomento per controllare il tipo di confronto: `Text` per la maggior parte degli input e output `Binary` per determinare le corrispondenze esatte.  
  
 Il `StrComp` funzione restituisce un intero che indica la relazione tra le due stringhe confrontate in base all'ordine di ordinamento. Un valore positivo per il risultato indica che la prima stringa è maggiore della seconda stringa. Un risultato negativo indica la prima stringa è minore, mentre zero indica che l'uguaglianza tra le stringhe.  
  
 [!code-vb[VbVbalrStrings#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#22)]  
  
 È anche possibile usare la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] partner del `StrComp` funzione, il <xref:System.String.Compare%2A?displayProperty=nameWithType> (metodo). Si tratta di un metodo statico, overload della classe base string. L'esempio seguente illustra come viene utilizzato questo metodo:  
  
 [!code-vb[VbVbalrStrings#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#48)]  
  
 Per un maggiore controllo sul modo in cui vengono eseguiti i confronti, è possibile usare altri overload del <xref:System.String.Compare%2A> (metodo). Con il <xref:System.String.Compare%2A?displayProperty=nameWithType> metodo, è possibile usare il `comparisonType` argomento per specificare il tipo di confronto da usare.  
  
|Valore per `comparisonType` argomento|Tipo di confronto|Quando utilizzarlo|  
|---|---|---|  
|`Ordinal`|Confronto è basato sul byte componente stringhe.|Usare questo valore quando si confrontano: gli identificatori tra maiuscole e minuscole, impostazioni relative alla sicurezza o altri identificatori non linguistico in cui i byte devono corrispondere esattamente.|  
|`OrdinalIgnoreCase`|Confronto è basato sul byte componente stringhe.<br /><br /> `OrdinalIgnoreCase` utilizza le informazioni sulle impostazioni cultura invarianti per determinare se due caratteri differiscono solo per maiuscole/minuscole.|Usare questo valore quando si confrontano: gli identificatori di maiuscole e minuscole, impostazioni relative alla sicurezza e i dati archiviati in Windows.|  
|`CurrentCulture` o `CurrentCultureIgnoreCase`|Confronto in base all'interpretazione delle stringhe nell'oggetto culture corrente.|Usare questi valori quando si confrontano: i dati visualizzati all'utente, la maggior parte degli input dell'utente e altri dati che richiede l'interpretazione linguistica.|  
|`InvariantCulture` o `InvariantCultureIgnoreCase`|Confronto in base all'interpretazione delle stringhe nelle impostazioni cultura invarianti.<br /><br /> Ciò si differenzia il `Ordinal` e `OrdinalIgnoreCase`, perché le impostazioni cultura invarianti vengono considerati caratteri di fuori dell'intervallo accettato caratteri invariante equivalenti.|Usare questi valori solo durante il confronto di rendere persistenti i dati o la visualizzazione dei dati linguisticamente rilevanti che richiedono un ordinamento fisso.|  
  
### <a name="security-considerations"></a>Considerazioni sulla sicurezza  
 Se decisioni relative alla sicurezza in base al risultato di un'operazione di modifica di maiuscole o confronto effettuate dall'applicazione, quindi l'operazione deve usare la <xref:System.String.Compare%2A?displayProperty=nameWithType> metodo e passare `Ordinal` o `OrdinalIgnoreCase` per il `comparisonType` argomento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization.CultureInfo>
- [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
