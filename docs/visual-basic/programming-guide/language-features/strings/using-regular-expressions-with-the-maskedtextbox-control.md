---
title: Utilizzo di espressioni regolari con il controllo MaskedTextBox in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: 25bdfaef300b001d1c052aeea4e1ad3547a6d3d7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43803810"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Utilizzo di espressioni regolari con il controllo MaskedTextBox in Visual Basic
In questo esempio viene illustrato come eseguire la conversione di espressioni regolari semplice da utilizzare con il <xref:System.Windows.Forms.MaskedTextBox> controllo.  
  
## <a name="description-of-the-masking-language"></a>Descrizione del linguaggio di definizione della maschera  
 Lo standard <xref:System.Windows.Forms.MaskedTextBox> maschera language è basata su quello utilizzato dal `Masked Edit` controllare in Visual Basic 6.0 e deve essere noto agli utenti di eseguire la migrazione di questa piattaforma.  
  
 Il <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà del <xref:System.Windows.Forms.MaskedTextBox> controllo specifica la maschera di input da usare. La maschera deve essere una stringa composta da uno o più degli elementi della maschera dalla tabella seguente.  
  
|Elemento di mascheramento|Descrizione|Elemento di espressione regolare|  
|---------------------|-----------------|--------------------------------|  
|0|Qualsiasi cifra singola compreso tra 0 e 9. Immettere i dati.|\d|  
|9|Cifra o lo spazio. Voce facoltativa.|[\d]?|  
|#|Cifra o lo spazio. Voce facoltativa. Se questa posizione viene lasciata vuota nella maschera, verrà visualizzata come spazio. Segno più (+) e meno (-) sono consentiti i segni.|[\d+-]?|  
|L|Lettera ASCII. Immettere i dati.|[a-zA-Z]|  
|?|Lettera ASCII. Voce facoltativa.|[a-zA-Z]?|  
|&|Carattere. Immettere i dati.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|Carattere. Voce facoltativa.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|Alfanumerico. Voce facoltativa.|\W|  
|.|Impostazioni cultura appropriata segnaposto decimale.|Non disponibile.|  
|,|Impostazioni cultura appropriata migliaia segnaposto.|Non disponibile.|  
|:|Separatore appropriato per la lingua dell'ora.|Non disponibile.|  
|/|Separatore appropriato per la lingua della data.|Non disponibile.|  
|$|Simbolo della valuta appropriato delle impostazioni cultura.|Non disponibile.|  
|\<|Converte tutti i caratteri che seguono in caratteri minuscoli.|Non disponibile.|  
|>|Converte tutti i caratteri che seguono in maiuscolo.|Non disponibile.|  
|&#124;|Annulla un cambiamento precedente backup oppure spostare verso il basso.|Non disponibile.|  
|&#92;|Esegue l'escape di un carattere della maschera, trasformandolo in un valore letterale. "\\\\" è la sequenza di escape per una barra rovesciata.|&#92;|  
|Tutti gli altri caratteri.|Valori letterali. Verranno visualizzati tutti gli elementi non maschera se stessi all'interno di <xref:System.Windows.Forms.MaskedTextBox>.|Tutti gli altri caratteri.|  
  
 Numero decimale (.), migliaia (,), tempi (:), data (/) e predefinito di simboli di valuta ($) i simboli di base a quanto definito dalle impostazioni cultura dell'applicazione. È possibile imporre loro di visualizzare i simboli delle altre impostazioni cultura usando le <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> proprietà.  
  
## <a name="regular-expressions-and-masks"></a>Le espressioni regolari e maschere  
 Sebbene sia possibile utilizzare le espressioni regolari e maschere per convalidare l'input dell'utente, non sono completamente equivalenti. Le espressioni regolari possono esprimere schemi più complessi rispetto alle maschere, ma possono esprimere le stesse informazioni più conciso e in un formato culturalmente pertinente.  
  
 La tabella seguente confronta le espressioni regolari quattro e la maschera equivalente per ognuna.  
  
|Espressione regolare|Maschera|Note|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|Il `/` carattere della maschera è un separatore di data logica, e verrà visualizzato all'utente come separatore della data appropriato alle impostazioni cultura correnti dell'applicazione.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Una data (giorno abbreviazione del mese e anno) nel formato di Stati Uniti in cui l'abbreviazione di tre lettere mese viene visualizzato con una lettera iniziale maiuscola seguita da due lettere minuscole.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Numero di telefono Stati Uniti, indicativo di località facoltativo. Se l'utente non desidera immettere i caratteri facoltativi, Anna può immettere gli spazi o posizionare il puntatore del mouse direttamente in corrispondenza della posizione della maschera rappresentato dal primo 0.|  
|`$\d{6}.00`|`$999,999.00`|Valore di valuta compreso nell'intervallo tra 0 e 999999. La valuta, millesimo e caratteri decimali verranno sostituiti in fase di esecuzione con i relativi equivalenti specifici delle impostazioni cultura.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [Convalida delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)  
 [Controllo MaskedTextBox](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
