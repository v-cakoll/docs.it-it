---
title: Utilizzo di espressioni regolari con il controllo MaskedTextBox in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72542c05123ef62a8f95afbe1bb19cb823d1f21
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Utilizzo di espressioni regolari con il controllo MaskedTextBox in Visual Basic
In questo esempio viene illustrato come convertire espressioni regolari semplice da utilizzare con il <xref:System.Windows.Forms.MaskedTextBox> controllo.  
  
## <a name="description-of-the-masking-language"></a>Descrizione del linguaggio per la  
 Lo standard <xref:System.Windows.Forms.MaskedTextBox> maschera linguaggio si basa su quello utilizzato per il `Masked Edit` controllare in Visual Basic 6.0 e dovrebbe essere noto agli utenti la migrazione da tale piattaforma.  
  
 Il <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà del <xref:System.Windows.Forms.MaskedTextBox> controllo specifica la maschera di input da utilizzare. La maschera deve essere una stringa composta da uno o più elementi di maschera dalla tabella seguente.  
  
|Elemento maschera|Descrizione|Elemento di espressione regolare|  
|---------------------|-----------------|--------------------------------|  
|0|Qualsiasi cifra compresa tra 0 e 9. Valore obbligatorio.|\d|  
|9|Numero o spazio. Voce facoltativa.|[\d]?|  
|#|Numero o spazio. Voce facoltativa. Se questa posizione viene lasciata vuota nella maschera, verrà visualizzata come spazio. Segno più (+) e meno (-) sono consentiti i segni.|[\d+-]?|  
|L|Lettera ASCII. Valore obbligatorio.|[a-zA-Z]|  
|?|Lettera ASCII. Voce facoltativa.|[a-zA-Z]?|  
|&|Carattere. Valore obbligatorio.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|Carattere. Voce facoltativa.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|Alfanumerico. Voce facoltativa.|\W|  
|.|Segnaposto decimale appropriato per la lingua.|Non disponibile.|  
|,|Segnaposto appropriato per la lingua migliaia.|Non disponibile.|  
|:|Separatore dell'ora appropriato per la lingua.|Non disponibile.|  
|/|Separatore di data appropriato per la lingua.|Non disponibile.|  
|$|Simbolo di valuta appropriato per la lingua.|Non disponibile.|  
|\<|Converte tutti i caratteri che seguono in caratteri minuscoli.|Non disponibile.|  
|>|Converte tutti i caratteri che seguono in lettere maiuscole.|Non disponibile.|  
|&#124;|Annulla un turno precedente backup o di spostarsi verso il basso.|Non disponibile.|  
|\|Esegue l'escape di un carattere di maschera, trasformandolo in un valore letterale. "\\\\" è la sequenza di escape per una barra rovesciata.|\|  
|Tutti gli altri caratteri.|Valori letterali. Tutti gli elementi non maschera verranno visualizzati come tali all'interno di <xref:System.Windows.Forms.MaskedTextBox>.|Tutti gli altri caratteri.|  
  
 Separatore decimale (.), migliaia (,), ora (:), data (/) e predefinito di simboli di valuta ($) per i simboli definiti dalle impostazioni cultura dell'applicazione. Per imporre la visualizzazione dei simboli di altre impostazioni cultura utilizzando il <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> proprietà.  
  
## <a name="regular-expressions-and-masks"></a>Espressioni regolari e maschere  
 Sebbene sia possibile utilizzare espressioni regolari e maschere per convalidare l'input dell'utente, non sono completamente equivalente. Espressioni regolari in grado di esprimere modelli più complessi rispetto alle maschere, ma possono esprimere le stesse informazioni più conciso e in un formato alla lingua.  
  
 Nella tabella seguente confronta quattro espressioni regolari e la maschera equivalente per ognuna.  
  
|Espressione regolare|Maschera|Note|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|Il `/` carattere della maschera è un separatore di data logica e verrà visualizzato dall'utente come separatore della data appropriato per la lingua corrente dell'applicazione.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Data in formato di Stati Uniti in cui viene visualizzata l'abbreviazione del mese di tre lettere con lettera iniziale maiuscola seguita da due lettere minuscole (giorno, abbreviazione del mese e anno).|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Numero di telefono degli Stati Uniti, prefisso facoltativo. Se l'utente non desidera immettere i caratteri facoltativi, è possibile immettere spazi o posizionare il puntatore del mouse direttamente in corrispondenza della posizione della maschera rappresentata dal primo 0.|  
|`$\d{6}.00`|`$999,999.00`|Un valore di valuta compreso nell'intervallo tra 0 e 999999. Caratteri decimali, valuta e millesimo verranno sostituiti in fase di esecuzione con i relativi equivalenti specifici delle impostazioni cultura.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [Convalida delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)  
 [Controllo MaskedTextBox](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
