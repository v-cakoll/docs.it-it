---
title: Influenza delle impostazioni cultura sulle stringhe
ms.date: 07/20/2015
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
ms.openlocfilehash: 2520a7684b8710abd949543e3f17f77d3c631d22
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352470"
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Influenza delle impostazioni cultura sulle stringhe in Visual Basic
Questa pagina della guida illustra il modo in cui Visual Basic usa le informazioni sulle impostazioni cultura per eseguire confronti e conversioni di stringhe.  
  
## <a name="when-to-use-culture-specific-strings"></a>Quando usare stringhe specifiche delle impostazioni cultura  
 In genere, è consigliabile usare stringhe specifiche delle impostazioni cultura per tutti i dati presentati e letti dagli utenti e usare stringhe indipendenti dalle impostazioni cultura per i dati interni dell'applicazione.  
  
 Se, ad esempio, l'applicazione richiede agli utenti di immettere una data come stringa, è necessario che gli utenti configurano le stringhe in base alle rispettive impostazioni cultura e che l'applicazione converta la stringa in modo appropriato. Se l'applicazione presenta tale data nell'interfaccia utente, deve presentarla nelle impostazioni cultura dell'utente.  
  
 Tuttavia, se l'applicazione carica la data in un server centrale, deve formattare la stringa in base a una lingua specifica, per evitare confusione tra formati di data potenzialmente diversi.  
  
## <a name="culture-sensitive-functions"></a>Funzioni dipendenti dalle impostazioni cultura  
 Tutte le funzioni di conversione di stringhe Visual Basic (ad eccezione delle funzioni `Str` e `Val`) utilizzano le informazioni sulle impostazioni cultura dell'applicazione per assicurarsi che le conversioni e i confronti siano appropriati per le impostazioni cultura dell'utente dell'applicazione.  
  
 La chiave per usare correttamente le funzioni di conversione delle stringhe nelle applicazioni eseguite su computer con impostazioni cultura diverse è quella di comprendere quali funzioni usano un'impostazione di impostazioni cultura specifica e che usano le impostazioni cultura correnti. Si noti che le impostazioni cultura dell'applicazione sono, per impostazione predefinita, ereditate dalle impostazioni cultura del sistema operativo. Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>e [funzioni di conversione dei tipi](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Il `Str` (converte i numeri in stringhe) e le funzioni `Val` (converte le stringhe in numeri) non usano le informazioni sulle impostazioni cultura dell'applicazione durante la conversione tra stringhe e numeri. Ma riconoscono solo il punto (.) come separatore decimale valido. Gli analoghi compatibili con la cultura di queste funzioni sono:  
  
- **Conversioni che usano le impostazioni cultura correnti.** Le funzioni `CStr` e `Format` convertono un numero in una stringa e le funzioni `CDbl` e `CInt` convertono una stringa in un numero.  
  
- **Conversioni che usano impostazioni cultura specifiche.** Ogni oggetto Number dispone di un metodo `ToString(IFormatProvider)` che converte un numero in una stringa e un metodo `Parse(String, IFormatProvider)` che converte una stringa in un numero. Il tipo `Double`, ad esempio, fornisce i metodi <xref:System.Double.ToString%28System.IFormatProvider%29> e <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29>.  
  
 Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Conversion.Str%2A> e <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## <a name="using-a-specific-culture"></a>Uso di impostazioni cultura specifiche  
 Si supponga di sviluppare un'applicazione che invii una data (formattata come stringa) a un servizio Web. In questo caso, l'applicazione deve usare impostazioni cultura specifiche per la conversione di stringhe. Per illustrare il motivo, considerare il risultato dell'uso del metodo di <xref:System.DateTime.ToString> della data: se l'applicazione usa tale metodo per formattare la data del 4 luglio 2005, restituisce "7/4/2005 12:00:00 AM" quando viene eseguito con le impostazioni cultura Stati Uniti inglese (en-US), ma restituisce "04.07.2005 00:00:00" quando viene eseguito con le impostazioni cultura tedesche (de-DE).  
  
 Quando è necessario eseguire una conversione di stringa in un formato di impostazioni cultura specifico, è necessario usare la classe `CultureInfo` compilata nel .NET Framework. È possibile creare un nuovo oggetto `CultureInfo` per impostazioni cultura specifiche passando il nome delle impostazioni cultura al costruttore di <xref:System.Globalization.CultureInfo.%23ctor%2A>. I nomi delle impostazioni cultura supportati sono elencati nella pagina della guida della classe <xref:System.Globalization.CultureInfo>.  
  
 In alternativa, è possibile ottenere un'istanza della *lingua inglese* dalla proprietà <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Le impostazioni cultura invarianti sono basate sulle impostazioni cultura inglesi, ma esistono alcune differenze. La lingua inglese, ad esempio, specifica un formato a 24 ore anziché un orologio a 12 ore.  
  
 Per convertire una data nella stringa delle impostazioni cultura, passare l'oggetto <xref:System.Globalization.CultureInfo> al metodo <xref:System.DateTime.ToString%28System.IFormatProvider%29> dell'oggetto Data. Il codice seguente, ad esempio, Visualizza "07/04/2005 00:00:00", indipendentemente dalle impostazioni cultura dell'applicazione.  
  
 [!code-vb[VbVbalrConcepts#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#1)]  
  
> [!NOTE]
> I valori letterali di data vengono sempre interpretati in base alle impostazioni cultura inglesi.  
  
## <a name="comparing-strings"></a>Confronto di stringhe  
 Esistono due situazioni importanti in cui sono necessari confronti tra stringhe:  
  
- **Ordinamento dei dati da visualizzare all'utente.** Utilizzare le operazioni basate sulle impostazioni cultura correnti in modo che le stringhe vengano ordinate in modo appropriato.  
  
- **Determinare se due stringhe interne dell'applicazione corrispondono esattamente (in genere per motivi di sicurezza).** Utilizzare le operazioni che ignorano le impostazioni cultura correnti.  
  
 È possibile eseguire entrambi i tipi di confronti con la funzione Visual Basic <xref:Microsoft.VisualBasic.Strings.StrComp%2A>. Specificare l'argomento facoltativo `Compare` per controllare il tipo di confronto: `Text` per la maggior parte degli `Binary` di input e output per determinare le corrispondenze esatte.  
  
 La funzione `StrComp` restituisce un intero che indica la relazione tra le due stringhe confrontate in base all'ordinamento. Un valore positivo per il risultato indica che la prima stringa è maggiore della seconda. Un risultato negativo indica che la prima stringa è più piccola e zero indica l'uguaglianza tra le stringhe.  
  
 [!code-vb[VbVbalrStrings#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#22)]  
  
 È anche possibile usare il partner .NET Framework della funzione `StrComp`, il <xref:System.String.Compare%2A?displayProperty=nameWithType> metodo. Si tratta di un metodo statico di overload della classe String di base. Nell'esempio seguente viene illustrato il modo in cui viene utilizzato questo metodo:  
  
 [!code-vb[VbVbalrStrings#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#48)]  
  
 Per un controllo più preciso sulla modalità di esecuzione dei confronti, è possibile utilizzare overload aggiuntivi del metodo <xref:System.String.Compare%2A>. Con il metodo <xref:System.String.Compare%2A?displayProperty=nameWithType>, è possibile utilizzare l'argomento `comparisonType` per specificare il tipo di confronto da utilizzare.  
  
|Valore per l'argomento `comparisonType`|Tipo di confronto|Quando utilizzarlo|  
|---|---|---|  
|`Ordinal`|Confronto basato sui byte dei componenti delle stringhe.|Utilizzare questo valore quando si confrontano gli identificatori con distinzione tra maiuscole e minuscole, le impostazioni relative alla sicurezza o altri identificatori non linguistici in cui i byte devono corrispondere esattamente.|  
|`OrdinalIgnoreCase`|Confronto basato sui byte dei componenti delle stringhe.<br /><br /> `OrdinalIgnoreCase` usa le informazioni sulle impostazioni cultura invarianti per determinare quando due caratteri differiscono solo per le maiuscole.|Utilizzare questo valore quando si confrontano gli identificatori senza distinzione tra maiuscole e minuscole, le impostazioni relative alla sicurezza e i dati archiviati in Windows.|  
|`CurrentCulture` o `CurrentCultureIgnoreCase`|Confronto basato sull'interpretazione delle stringhe nelle impostazioni cultura correnti.|Usare questi valori durante il confronto: dati visualizzati all'utente, la maggior parte dell'input utente e altri dati che richiedono l'interpretazione linguistica.|  
|`InvariantCulture` o `InvariantCultureIgnoreCase`|Confronto basato sull'interpretazione delle stringhe nelle impostazioni cultura invarianti.<br /><br /> Si tratta di un valore diverso da quello `Ordinal` e `OrdinalIgnoreCase`, perché la lingua inglese considera i caratteri al di fuori dell'intervallo accettato come caratteri invarianti equivalenti.|Usare questi valori solo quando si confrontano i dati in modo permanente o si visualizzano dati pertinenti linguisticamente che richiedono un ordinamento fisso.|  
  
### <a name="security-considerations"></a>Considerazioni sulla sicurezza  
 Se l'applicazione prende decisioni di sicurezza in base al risultato di un'operazione di confronto o di modifica di maiuscole e minuscole, l'operazione deve usare il metodo <xref:System.String.Compare%2A?displayProperty=nameWithType> e passare `Ordinal` o `OrdinalIgnoreCase` per l'argomento `comparisonType`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization.CultureInfo>
- [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [CString](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
