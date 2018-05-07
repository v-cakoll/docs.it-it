---
title: Utilizzo efficiente dei tipi di dati (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 6e71c4e2225bbcde3bb2bd20ae098f5600990051
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="efficient-use-of-data-types-visual-basic"></a>Utilizzo efficiente dei tipi di dati (Visual Basic)
Le variabili non dichiarate e le variabili dichiarate senza un tipo di dati vengono assegnate i `Object` tipo di dati. Ciò semplifica la scrittura di programmi rapidamente, ma è possibile che vengano eseguite più lentamente.  
  
## <a name="strong-typing"></a>Tipizzazione forte  
 Specifica di tipi di dati per tutte le variabili è noto come *tipizzazione forte*. Con la tipizzazione forte presenta diversi vantaggi:  
  
-   Consente il supporto IntelliSense per le variabili. In questo modo è possibile visualizzare le relative proprietà e gli altri membri durante la digitazione nel codice.  
  
-   Consente di usufruire del compilatore verifica dei tipi. Questo memorizza nella cache le istruzioni che possono avere esito negativo in fase di esecuzione a causa di errori, ad esempio l'overflow. Vengono inoltre rilevate le chiamate ai metodi su oggetti che non li supportano.  
  
-   Comporta tempi di esecuzione del codice.  
  
## <a name="most-efficient-data-types"></a>Tipi di dati più efficienti  
 Per le variabili che non contengono mai frazioni, i tipi di dati integrali sono più efficienti rispetto ai tipi non integrali. In Visual Basic `Integer` e `UInteger` sono i tipi numerici più efficienti.  
  
 Per i numeri frazionari, `Double` è il tipo di dati più efficiente, perché i processori disponibili sulle attuali piattaforme eseguono operazioni a virgola mobile e precisione doppia. Tuttavia, le operazioni con `Double` non sono veloci come con i tipi integrali, ad esempio `Integer`.  
  
## <a name="specifying-data-type"></a>Specifica il tipo di dati  
 Utilizzare il [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) per dichiarare una variabile di un tipo specifico. Contemporaneamente, è possibile specificare il livello di accesso tramite il [pubblica](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privata](../../../../visual-basic/language-reference/modifiers/private.md) (parola chiave), come nel esempio seguente.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>Conversione dei caratteri  
 Il `AscW` e `ChrW` funzioni sono in formato Unicode. È necessario utilizzarli a `Asc` e `Chr`, che devono essere convertite in Unicode.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipi di dati numerici](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Utilizzo di IntelliSense](/visualstudio/ide/using-intellisense)
