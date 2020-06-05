---
title: Uso di espressioni regolari con il controllo MaskedTextBox
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: efda70be0ccdbc1f4b59d548e50f743f6c493b19
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363714"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Utilizzo di espressioni regolari con il controllo MaskedTextBox in Visual Basic
Questo esempio illustra come convertire semplici espressioni regolari per lavorare con il <xref:System.Windows.Forms.MaskedTextBox> controllo.  
  
## <a name="description-of-the-masking-language"></a>Descrizione della lingua di maschera  
 Il <xref:System.Windows.Forms.MaskedTextBox> linguaggio di maschera standard è basato su quello utilizzato dal `Masked Edit` controllo in Visual Basic 6,0 e deve essere familiare agli utenti che eseguono la migrazione da tale piattaforma.  
  
 La <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà del <xref:System.Windows.Forms.MaskedTextBox> controllo specifica quale maschera di input usare. La maschera deve essere una stringa composta da uno o più elementi di maschera della tabella seguente.  
  
|Elemento mascheramento|Descrizione|Elemento Regular Expression|  
|---------------------|-----------------|--------------------------------|  
|0|Ogni singola cifra compresa tra 0 e 9. È necessaria una voce.|\d|  
|9|Cifra o spazio. Voce facoltativa.|[\d]?|  
|#|Cifra o spazio. Voce facoltativa. Se questa posizione viene lasciata vuota nella maschera, ne verrà eseguito il rendering come spazio. Sono consentiti segni più (+) e meno (-).|[\d +-]?|  
|L|Lettera ASCII. È necessaria una voce.|[a-zA-Z]|  
|?|Lettera ASCII. Voce facoltativa.|[a-zA-Z]?|  
|&|Carattere. È necessaria una voce.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|Carattere. Voce facoltativa.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|Una|Alfanumerici. Voce facoltativa.|\W|  
|.|Segnaposto decimale appropriato per le impostazioni cultura.|Non disponibile.|  
|,|Impostazioni cultura: segnaposto di migliaia appropriato.|Non disponibile.|  
|:|Impostazioni cultura-separatore ora appropriato.|Non disponibile.|  
|/|Impostazioni cultura-separatore data appropriato.|Non disponibile.|  
|$|Impostazioni cultura-simbolo di valuta appropriato.|Non disponibile.|  
|\<|Converte tutti i caratteri che seguono in lettere minuscole.|Non disponibile.|  
|>|Converte tutti i caratteri che seguono in maiuscolo.|Non disponibile.|  
|&#124;|Annulla uno spostamento precedente verso l'alto o verso il basso.|Non disponibile.|  
|&#92;|Esclude un carattere di maschera, trasformandolo in un valore letterale. " \\ \\ " è la sequenza di escape per una barra rovesciata.|&#92;|  
|Tutti gli altri caratteri.|Valori letterali. Tutti gli elementi non maschera verranno visualizzati come se fossero all'interno di <xref:System.Windows.Forms.MaskedTextBox> .|Tutti gli altri caratteri.|  
  
 Per impostazione predefinita, i simboli decimali (.), millesimi (,), Time (:), date (/) e Currency ($) per visualizzare i simboli come definito dalle impostazioni cultura dell'applicazione. È possibile forzare la visualizzazione dei simboli per altre impostazioni cultura tramite la <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> Proprietà.  
  
## <a name="regular-expressions-and-masks"></a>Espressioni regolari e maschere  
 Sebbene sia possibile utilizzare espressioni regolari e maschere per convalidare l'input dell'utente, non sono completamente equivalenti. Le espressioni regolari possono esprimere modelli più complessi rispetto alle maschere, ma le maschere possono esprimere le stesse informazioni in maniera più concisa e in un formato culturalmente pertinente.  
  
 Nella tabella seguente vengono confrontate quattro espressioni regolari e la maschera equivalente per ciascuna di esse.  
  
|Espressione regolare|Mask|Note|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|Il `/` carattere nella maschera è un separatore di data logico e verrà visualizzato all'utente come separatore della data appropriato per le impostazioni cultura correnti dell'applicazione.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Data (giorno, abbreviazione del mese e anno) nel formato Stati Uniti, in cui l'abbreviazione del mese di tre lettere viene visualizzata con una lettera maiuscola iniziale seguita da due lettere minuscole.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Stati Uniti numero di telefono, codice area facoltativo. Se l'utente non vuole immettere i caratteri facoltativi, può immettere spazi o posizionare il puntatore del mouse direttamente nella posizione nella maschera rappresentata dal primo 0.|  
|`$\d{6}.00`|`$999,999.00`|Valore di valuta compreso nell'intervallo tra 0 e 999999. I caratteri di valuta, millesimo e decimale verranno sostituiti in fase di esecuzione con gli equivalenti specifici delle impostazioni cultura.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>
- <xref:System.Windows.Forms.MaskedTextBox>
- [Convalida delle stringhe in Visual Basic](validating-strings.md)
- [Controllo MaskedTextBox](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
