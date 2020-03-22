---
title: Uso di espressioni regolari con il controllo MaskedTextBox
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: b997f6f495fca51e888bb995fee0361d29d68048
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148284"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Utilizzo di espressioni regolari con il controllo MaskedTextBox in Visual Basic
In questo esempio viene illustrato come convertire <xref:System.Windows.Forms.MaskedTextBox> semplici espressioni regolari da utilizzare con il controllo.  
  
## <a name="description-of-the-masking-language"></a>Descrizione del linguaggio di mascheramento  
 Il <xref:System.Windows.Forms.MaskedTextBox> linguaggio di mascheramento standard è `Masked Edit` basato su quello utilizzato dal controllo in Visual Basic 6.0 e deve essere familiare agli utenti che eseguono la migrazione da tale piattaforma.  
  
 La <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà <xref:System.Windows.Forms.MaskedTextBox> del controllo specifica la maschera di input da utilizzare. La maschera deve essere una stringa composta da uno o più elementi maschera della tabella seguente.  
  
|Elemento maschera|Descrizione|Elemento di espressione regolare|  
|---------------------|-----------------|--------------------------------|  
|0|Qualsiasi cifra singola compresa tra 0 e 9. Immissione obbligatoria.|\d|  
|9|Cifra o spazio. Immissione facoltativa.|[ d]?|  
|#|Cifra o spazio. Immissione facoltativa. Se questa posizione viene lasciata vuota nella maschera, verrà visualizzata come spazio. Sono consentiti i segni più e meno (-).|[d--]?|  
|L|Lettera ASCII. Immissione obbligatoria.|[a-zA-z]|  
|?|Lettera ASCII. Immissione facoltativa.|[a-zA-z]?|  
|&|Carattere. Immissione obbligatoria.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|Carattere. Immissione facoltativa.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|Una |Alfanumerici. Immissione facoltativa.|\W|  
|.|Segnaposto decimale appropriato per le impostazioni cultura.|Non disponibile.|  
|,|Segnaposto delle migliaia appropriato per le impostazioni cultura.|Non disponibile.|  
|:|Separatore dell'ora appropriato per le impostazioni cultura.|Non disponibile.|  
|/|Separatore di data appropriato per le impostazioni cultura.|Non disponibile.|  
|$|Simbolo di valuta appropriato per le impostazioni cultura.|Non disponibile.|  
|\<|Converte tutti i caratteri che seguono in minuscolo.|Non disponibile.|  
|>|Converte tutti i caratteri che seguono in maiuscolo.|Non disponibile.|  
|&#124;|Annulla uno spostamento precedente verso l'alto o verso il basso.|Non disponibile.|  
|&#92;|Esegue l'escape di un carattere maschera, trasformandolo in un valore letterale. "\\\\" è la sequenza di escape per una barra rovesciata.|&#92;|  
|Tutti gli altri caratteri.|Valori letterali. Tutti gli elementi non maschera <xref:System.Windows.Forms.MaskedTextBox>verranno visualizzati come se stessi all'interno di .|Tutti gli altri caratteri.|  
  
 Per impostazione predefinita, i simboli decimali (.), dei millesimi (,), dell'ora (:), della data (/) e della valuta (-) visualizzano i simboli definiti dalle impostazioni cultura dell'applicazione. È possibile forzare la visualizzazione dei <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> simboli per altre impostazioni cultura utilizzando la proprietà .  
  
## <a name="regular-expressions-and-masks"></a>Espressioni regolari e maschere  
 Sebbene sia possibile utilizzare espressioni regolari e maschere per convalidare l'input dell'utente, non sono completamente equivalenti. Le espressioni regolari possono esprimere modelli più complessi rispetto alle maschere, ma le maschere possono esprimere le stesse informazioni in modo più conciso e in un formato culturalmente rilevante.  
  
 Nella tabella seguente vengono confrontate quattro espressioni regolari e la maschera equivalente per ciascuna.  
  
|Espressione regolare|Mask|Note|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|Il `/` carattere nella maschera è un separatore di data logico e verrà visualizzato all'utente come separatore di data appropriato per le impostazioni cultura correnti dell'applicazione.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Data (giorno, abbreviazione del mese e anno) in formato Stati Uniti in cui l'abbreviazione di tre lettere del mese viene visualizzata con una lettera maiuscola iniziale seguita da due lettere minuscole.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Numero di telefono degli Stati Uniti, prefisso opzionale. Se l'utente non desidera immettere i caratteri facoltativi, può inserire spazi o posizionare il puntatore del mouse direttamente nella posizione nella maschera rappresentata dal primo 0.|  
|`$\d{6}.00`|`$999,999.00`|Valore di valuta compreso tra 0 e 999999. La valuta, il millesimo e i caratteri decimali verranno sostituiti in fase di esecuzione con i rispettivi equivalenti specifici delle impostazioni cultura.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>
- <xref:System.Windows.Forms.MaskedTextBox>
- [Convalida delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
- [Controllo MaskedTextBox](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
