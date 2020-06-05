---
title: Influenza delle impostazioni cultura sulle stringhe
ms.date: 07/20/2015
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
ms.openlocfilehash: 9cbd3a5b8685178259b76d97919ea097ae72f6ae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401966"
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Influenza delle impostazioni cultura sulle stringhe in Visual Basic
Questa pagina della guida illustra il modo in cui Visual Basic usa le informazioni sulle impostazioni cultura per eseguire confronti e conversioni di stringhe.  
  
## <a name="when-to-use-culture-specific-strings"></a>Quando usare stringhe specifiche delle impostazioni cultura  
 In genere, è consigliabile usare stringhe specifiche delle impostazioni cultura per tutti i dati presentati e letti dagli utenti e usare stringhe indipendenti dalle impostazioni cultura per i dati interni dell'applicazione.  
  
 Se, ad esempio, l'applicazione richiede agli utenti di immettere una data come stringa, è necessario che gli utenti configurano le stringhe in base alle rispettive impostazioni cultura e che l'applicazione converta la stringa in modo appropriato. Se l'applicazione presenta tale data nell'interfaccia utente, deve presentarla nelle impostazioni cultura dell'utente.  
  
 Tuttavia, se l'applicazione carica la data in un server centrale, deve formattare la stringa in base a una lingua specifica, per evitare confusione tra formati di data potenzialmente diversi.  
  
## <a name="culture-sensitive-functions"></a>Funzioni dipendenti dalle impostazioni cultura  
 Tutte le funzioni di conversione di stringhe Visual Basic (ad eccezione delle `Str` `Val` funzioni e) utilizzano le informazioni sulle impostazioni cultura dell'applicazione per assicurarsi che le conversioni e i confronti siano appropriati per le impostazioni cultura dell'utente dell'applicazione.  
  
 La chiave per usare correttamente le funzioni di conversione delle stringhe nelle applicazioni eseguite su computer con impostazioni cultura diverse è quella di comprendere quali funzioni usano un'impostazione di impostazioni cultura specifica e che usano le impostazioni cultura correnti. Si noti che le impostazioni cultura dell'applicazione sono, per impostazione predefinita, ereditate dalle impostazioni cultura del sistema operativo. Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Asc%2A> , <xref:Microsoft.VisualBasic.Strings.AscW%2A> , <xref:Microsoft.VisualBasic.Strings.Chr%2A> , <xref:Microsoft.VisualBasic.Strings.ChrW%2A> , <xref:Microsoft.VisualBasic.Strings.Format%2A> , <xref:Microsoft.VisualBasic.Conversion.Hex%2A> , <xref:Microsoft.VisualBasic.Conversion.Oct%2A> e [funzioni di conversione del tipo](../../../language-reference/functions/type-conversion-functions.md).  
  
 Le `Str` funzioni (converte i numeri in stringhe) e `Val` (converte le stringhe in numeri) non usano le informazioni sulle impostazioni cultura dell'applicazione durante la conversione tra stringhe e numeri. Ma riconoscono solo il punto (.) come separatore decimale valido. Gli analoghi compatibili con la cultura di queste funzioni sono:  
  
- **Conversioni che usano le impostazioni cultura correnti.** Le `CStr` `Format` funzioni e convertono un numero in una stringa e le `CDbl` `CInt` funzioni e convertono una stringa in un numero.  
  
- **Conversioni che usano impostazioni cultura specifiche.** Ogni oggetto Number dispone di un `ToString(IFormatProvider)` metodo che converte un numero in una stringa e un `Parse(String, IFormatProvider)` metodo che converte una stringa in un numero. Il tipo, ad esempio, `Double` fornisce <xref:System.Double.ToString%28System.IFormatProvider%29> i <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> metodi e.  
  
 Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Conversion.Str%2A> e <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## <a name="using-a-specific-culture"></a>Uso di impostazioni cultura specifiche  
 Si supponga di sviluppare un'applicazione che invii una data (formattata come stringa) a un servizio Web. In questo caso, l'applicazione deve usare impostazioni cultura specifiche per la conversione di stringhe. Per illustrare il motivo, considerare il risultato dell'uso del metodo della data <xref:System.DateTime.ToString> : se l'applicazione usa tale metodo per formattare la data del 4 luglio 2005, restituisce "7/4/2005 12:00:00 AM" quando viene eseguito con le impostazioni cultura Stati Uniti inglese (en-US), ma restituisce "04.07.2005 00:00:00" quando viene eseguito con le impostazioni cultura tedesche (de-de).  
  
 Quando è necessario eseguire una conversione di stringa in un formato di impostazioni cultura specifico, è necessario usare la `CultureInfo` classe incorporata nel .NET Framework. È possibile creare un nuovo `CultureInfo` oggetto per impostazioni cultura specifiche passando il nome delle impostazioni cultura al <xref:System.Globalization.CultureInfo.%23ctor%2A> costruttore. I nomi delle impostazioni cultura supportati sono elencati nella pagina della Guida relativa alla <xref:System.Globalization.CultureInfo> classe.  
  
 In alternativa, è possibile ottenere un'istanza della *lingua inglese* dalla <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> Proprietà. Le impostazioni cultura invarianti sono basate sulle impostazioni cultura inglesi, ma esistono alcune differenze. La lingua inglese, ad esempio, specifica un formato a 24 ore anziché un orologio a 12 ore.  
  
 Per convertire una data nella stringa delle impostazioni cultura, passare l' <xref:System.Globalization.CultureInfo> oggetto al metodo dell'oggetto data <xref:System.DateTime.ToString%28System.IFormatProvider%29> . Il codice seguente, ad esempio, Visualizza "07/04/2005 00:00:00", indipendentemente dalle impostazioni cultura dell'applicazione.  
  
 [!code-vb[VbVbalrConcepts#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#1)]  
  
> [!NOTE]
> I valori letterali di data vengono sempre interpretati in base alle impostazioni cultura inglesi.  
  
## <a name="comparing-strings"></a>Confronto di stringhe  
 Esistono due situazioni importanti in cui sono necessari confronti tra stringhe:  
  
- **Ordinamento dei dati da visualizzare all'utente.** Utilizzare le operazioni basate sulle impostazioni cultura correnti in modo che le stringhe vengano ordinate in modo appropriato.  
  
- **Determinare se due stringhe interne dell'applicazione corrispondono esattamente (in genere per motivi di sicurezza).** Utilizzare le operazioni che ignorano le impostazioni cultura correnti.  
  
 È possibile eseguire entrambi i tipi di confronti con la <xref:Microsoft.VisualBasic.Strings.StrComp%2A> funzione Visual Basic. Specificare l' `Compare` argomento facoltativo per controllare il tipo di confronto: `Text` per la maggior parte dell'input e dell'output `Binary` per la determinazione delle corrispondenze esatte.  
  
 La `StrComp` funzione restituisce un intero che indica la relazione tra le due stringhe confrontate in base all'ordinamento. Un valore positivo per il risultato indica che la prima stringa è maggiore della seconda. Un risultato negativo indica che la prima stringa è più piccola e zero indica l'uguaglianza tra le stringhe.  
  
 [!code-vb[VbVbalrStrings#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#22)]  
  
 È anche possibile usare il partner .NET Framework della `StrComp` funzione, il <xref:System.String.Compare%2A?displayProperty=nameWithType> metodo. Si tratta di un metodo statico di overload della classe String di base. Nell'esempio seguente viene illustrato il modo in cui viene utilizzato questo metodo:  
  
 [!code-vb[VbVbalrStrings#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#48)]  
  
 Per un controllo più preciso sulla modalità di esecuzione dei confronti, è possibile utilizzare overload aggiuntivi del <xref:System.String.Compare%2A> metodo. Con il <xref:System.String.Compare%2A?displayProperty=nameWithType> metodo, è possibile usare l' `comparisonType` argomento per specificare il tipo di confronto da usare.  
  
|Valore per `comparisonType` argument|Tipo di confronto|Utilizzo|  
|---|---|---|  
|`Ordinal`|Confronto basato sui byte dei componenti delle stringhe.|Utilizzare questo valore quando si confrontano gli identificatori con distinzione tra maiuscole e minuscole, le impostazioni relative alla sicurezza o altri identificatori non linguistici in cui i byte devono corrispondere esattamente.|  
|`OrdinalIgnoreCase`|Confronto basato sui byte dei componenti delle stringhe.<br /><br /> `OrdinalIgnoreCase`Usa le informazioni sulle impostazioni cultura invarianti per determinare quando due caratteri differiscono solo per le maiuscole.|Utilizzare questo valore quando si confrontano gli identificatori senza distinzione tra maiuscole e minuscole, le impostazioni relative alla sicurezza e i dati archiviati in Windows.|  
|`CurrentCulture` o `CurrentCultureIgnoreCase`|Confronto basato sull'interpretazione delle stringhe nelle impostazioni cultura correnti.|Usare questi valori durante il confronto: dati visualizzati all'utente, la maggior parte dell'input utente e altri dati che richiedono l'interpretazione linguistica.|  
|`InvariantCulture` o `InvariantCultureIgnoreCase`|Confronto basato sull'interpretazione delle stringhe nelle impostazioni cultura invarianti.<br /><br /> Si tratta di un valore diverso da `Ordinal` e `OrdinalIgnoreCase` , perché la lingua inglese considera i caratteri al di fuori dell'intervallo accettato come caratteri invarianti equivalenti.|Usare questi valori solo quando si confrontano i dati in modo permanente o si visualizzano dati pertinenti linguisticamente che richiedono un ordinamento fisso.|  
  
### <a name="security-considerations"></a>Considerazioni relative alla sicurezza  
 Se l'applicazione prende decisioni di sicurezza in base al risultato di un'operazione di confronto o di modifica di maiuscole e minuscole, l'operazione deve usare il <xref:System.String.Compare%2A?displayProperty=nameWithType> metodo e passare `Ordinal` o `OrdinalIgnoreCase` per l' `comparisonType` argomento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization.CultureInfo>
- [Introduzione alle stringhe in Visual Basic](introduction-to-strings.md)
- [CString](../../../language-reference/functions/type-conversion-functions.md)
