---
title: Influenza delle impostazioni cultura sulle stringhe in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c95dcc8d04725f7a072e8c8bc7fe058e53a95c05
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Influenza delle impostazioni cultura sulle stringhe in Visual Basic
Questa pagina della Guida viene illustrato come Visual Basic utilizza informazioni sulle impostazioni cultura per eseguire confronti e le conversioni di stringa.  
  
## <a name="when-to-use-culture-specific-strings"></a>Quando utilizzare le stringhe specifiche delle impostazioni cultura  
 In genere, si deve usare stringhe specifiche delle impostazioni cultura per tutti i dati presentati letti dagli utenti e utilizzare stringhe di impostazioni cultura invarianti per dati interni dell'applicazione.  
  
 Ad esempio, se l'applicazione richiede agli utenti di immettere una data come stringa, deve aspettarsi che gli utenti per formattare le stringhe secondo le impostazioni cultura e l'applicazione deve convertire la stringa in modo appropriato. Se l'applicazione presenta quindi tale data nell'interfaccia utente, deve presentare il nelle impostazioni cultura dell'utente.  
  
 Tuttavia, se l'applicazione carica la data in un server centrale, opportuno formattare la stringa in base alle impostazioni cultura specifiche, per evitare confusione tra formati di data potenzialmente diversi.  
  
## <a name="culture-sensitive-functions"></a>Funzioni dipendenti dalle impostazioni cultura  
 Tutte le funzioni di conversione di stringhe Visual Basic (tranne che per il `Str` e `Val` funzioni) utilizzare informazioni sulle impostazioni cultura dell'applicazione per assicurarsi che le conversioni e i confronti siano appropriati per le impostazioni cultura dell'applicazione utente.  
  
 La chiave per l'utilizzo corretto delle funzioni di conversione di stringhe nelle applicazioni eseguite in computer con diverse impostazioni cultura consiste nel comprendere quali funzioni utilizzano impostazioni cultura specifiche, e che utilizzano le impostazioni cultura correnti. Si noti che le impostazioni dell'applicazione delle impostazioni cultura sono, per impostazione predefinita, ereditate dalle impostazioni cultura del sistema operativo. Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, e [funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Il `Str` (converte i numeri in stringhe) e `Val` funzioni (conversione di stringhe in numeri) non utilizzano informazioni sulle impostazioni cultura dell'applicazione durante la conversione tra stringhe e numeri. Riconoscono invece solo il punto (.) come separatore decimale valido. Gli analoghi sensibili di queste funzioni sono:  
  
-   **Conversioni che usano le impostazioni cultura correnti.** Il `CStr` e `Format` funzioni convertono una stringa, un numero e `CDbl` e `CInt` funzioni convertono una stringa di un numero.  
  
-   **Conversioni che utilizzano impostazioni cultura specifiche.** Ogni oggetto number è un `ToString(IFormatProvider)` metodo che converte un numero in una stringa e un `Parse(String, IFormatProvider)` metodo che converte una stringa in un numero. Ad esempio, il `Double` tipo fornisce il <xref:System.Double.ToString%28System.IFormatProvider%29> e <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> metodi.  
  
 Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Conversion.Str%2A> e <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## <a name="using-a-specific-culture"></a>Usando impostazioni cultura  
 Si supponga che si sviluppa un'applicazione che invia una data (formattata come stringa) a un servizio Web. In questo caso, l'applicazione deve utilizzare specifiche impostazioni cultura per la conversione di stringa. Per illustrare il motivo, considerare i risultati ottenuti utilizzando la data <xref:System.DateTime.ToString> metodo: se l'applicazione utilizza questo metodo per formattare la data 4 luglio 2005, restituisce "7/4/2005 12:00:00 AM" viene eseguito con le impostazioni cultura inglese Stati Uniti (en-US), ma restituisce " 04.07.2005 00:00:00 "viene eseguito con le impostazioni cultura tedesco (de-DE).  
  
 Quando è necessario eseguire una conversione di stringhe in un formato specifico delle impostazioni cultura, è consigliabile utilizzare il `CultureInfo` classe incorporato nel [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. È possibile creare un nuovo `CultureInfo` oggetto per una lingua specifica passando il nome delle impostazioni cultura per il <xref:System.Globalization.CultureInfo.%23ctor%2A> costruttore. I nomi delle impostazioni cultura supportati sono elencati nel <xref:System.Globalization.CultureInfo> pagina della Guida di classe.  
  
 In alternativa, è possibile ottenere un'istanza di *impostazioni cultura invarianti* dal <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> proprietà. Le impostazioni cultura invarianti sono basata sulla lingua inglese, ma esistono alcune differenze. Le impostazioni cultura invarianti ad esempio, specificano un formato di 24 ore anziché un formato a 12 ore.  
  
 Per convertire una data nella stringa delle impostazioni cultura, passare il <xref:System.Globalization.CultureInfo> all'oggetto data <xref:System.DateTime.ToString%28System.IFormatProvider%29> metodo. Ad esempio, il codice seguente viene visualizzato "07/04/2005 00:00:00", indipendentemente dalle impostazioni cultura dell'applicazione.  
  
 [!code-vb[VbVbalrConcepts#1](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  Valori letterali data vengono sempre interpretati in base alla lingua inglese.  
  
## <a name="comparing-strings"></a>Confronto di stringhe  
 Esistono due situazioni importanti in cui sono necessari i confronti di stringhe:  
  
-   **Ordinamento dei dati da visualizzare all'utente.** Usare le operazioni in base alle impostazioni cultura correnti, in modo da stringhe di ordinamento in modo appropriato.  
  
-   **Determinare se due stringhe interne all'applicazione corrispondano esattamente (in genere per motivi di sicurezza).** Utilizzare le operazioni che non tengono conto delle impostazioni cultura correnti.  
  
 È possibile eseguire entrambi i tipi di confronti con Visual Basic <xref:Microsoft.VisualBasic.Strings.StrComp%2A> (funzione). Specificare l'opzione facoltativa `Compare` argomento per controllare il tipo di confronto: `Text` per la maggior parte degli input e output `Binary` per determinare le corrispondenze esatte.  
  
 Il `StrComp` funzione restituisce un intero che indica la relazione tra le due stringhe confrontate in base all'ordine di ordinamento. Un valore positivo per il risultato indica che la prima stringa è maggiore della seconda stringa. Un risultato negativo indica la prima stringa è minore, mentre zero indica l'uguaglianza tra le stringhe.  
  
 [!code-vb[VbVbalrStrings#22](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 È inoltre possibile utilizzare il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] partner del `StrComp` funzione, il <xref:System.String.Compare%2A?displayProperty=nameWithType> metodo. Questo è un metodo di overload, statico della classe base string. L'esempio seguente illustra l'utilizzo di questo metodo:  
  
 [!code-vb[VbVbalrStrings#48](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 Per un maggiore controllo sul modo in cui vengono eseguiti i confronti, è possibile utilizzare altri overload di <xref:System.String.Compare%2A> metodo. Con il <xref:System.String.Compare%2A?displayProperty=nameWithType> (metodo), è possibile utilizzare il `comparisonType` argomento per specificare il tipo di confronto da utilizzare.  
  
|Il valore per `comparisonType` argomento|Tipo di confronto|Quando utilizzarlo|  
|---|---|---|  
|`Ordinal`|Confronto in base ai byte componente stringhe.|Utilizzare questo valore quando si confrontano: gli identificatori di distinzione maiuscole/minuscole, le impostazioni relative alla sicurezza o altri identificatori non linguistico in cui i byte devono corrispondere esattamente.|  
|`OrdinalIgnoreCase`|Confronto in base ai byte componente stringhe.<br /><br /> `OrdinalIgnoreCase` utilizza le informazioni sulle impostazioni cultura invarianti per determinare se due caratteri differiscono solo per maiuscole/minuscole.|Utilizzare questo valore quando si confrontano: gli identificatori di distinzione tra maiuscole e le impostazioni relative alla sicurezza e i dati archiviati in Windows.|  
|`CurrentCulture` o `CurrentCultureIgnoreCase`|Confronto in base all'interpretazione delle stringhe nelle impostazioni cultura correnti.|Usare questi valori quando si confrontano: i dati visualizzati all'utente, la maggior parte degli input dell'utente e altri dati che richiedono l'interpretazione linguistica.|  
|`InvariantCulture` o `InvariantCultureIgnoreCase`|Confronto in base all'interpretazione delle stringhe nelle impostazioni cultura invarianti.<br /><br /> Ciò è diverso da quello di `Ordinal` e `OrdinalIgnoreCase`, perché le impostazioni cultura invarianti considera caratteri di fuori dell'intervallo accettato come caratteri invarianti equivalenti.|Utilizzare questi valori solo durante il confronto dei dati persistenti o la visualizzazione dei dati linguisticamente rilevanti che richiede un ordinamento fisso.|  
  
### <a name="security-considerations"></a>Considerazioni sulla sicurezza  
 Se l'applicazione prende decisioni di sicurezza in base al risultato di un'operazione di modifica di maiuscole o il confronto, quindi l'operazione deve utilizzare il <xref:System.String.Compare%2A?displayProperty=nameWithType> (metodo) e passare `Ordinal` o `OrdinalIgnoreCase` per il `comparisonType` argomento.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Globalization.CultureInfo>  
 [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
