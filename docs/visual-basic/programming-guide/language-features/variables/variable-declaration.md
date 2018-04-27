---
title: Dichiarazione di variabili in Visual Basic
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
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8edd0b65b08efd437cc35e8f58ed7ed423736920
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="variable-declaration-in-visual-basic"></a>Dichiarazione di variabili in Visual Basic
Si dichiara una variabile per specificare il nome e le caratteristiche. Istruzione di dichiarazione delle variabili è di [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md). La posizione e il contenuto è possibile determinare le caratteristiche della variabile.  
  
 Per le regole di denominazione variabile e considerazioni, vedere [nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Livelli di dichiarazione  
  
### <a name="local-and-member-variables"></a>Locale e le variabili membro  
 Oggetto *variabile locale* è una variabile dichiarata all'interno di una stored procedure. Un *variabile membro* è un membro di un tipo di Visual Basic; è dichiarato a livello di modulo, all'interno di una classe, struttura o modulo, ma non all'interno di tutte le procedure interne di tale classe, struttura o modulo.  
  
### <a name="shared-and-instance-variables"></a>Condivise e le variabili di istanza  
 In una classe o struttura, la categoria di una variabile membro dipende o meno è condiviso. Se è dichiarata con la [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) (parola chiave), è un *variabile condivisa*, ed esiste una copia singola condivisa tra tutte le istanze della classe o struttura.  
  
 In caso contrario è un *variabile di istanza*, e viene creata una copia separata per ogni istanza della classe o struttura. Una copia di una variabile di istanza specificata è disponibile solo per l'istanza della classe o struttura in cui è stato creato. È indipendente da una copia della variabile di istanza in qualsiasi altra istanza della classe o struttura.  
  
## <a name="declaring-data-type"></a>Dichiarazione del tipo di dati  
 Il [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola nell'istruzione di dichiarazione consente di definire il tipo di dati o un tipo di oggetto della variabile che si sta dichiarando. È possibile specificare i tipi seguenti di una variabile:  
  
-   Digitare un dati elementari, ad esempio `Boolean`, `Long`, o `Decimal`  
  
-   Un tipo di dati composta, ad esempio una matrice o una struttura  
  
-   Un tipo di oggetto o una classe, definito nell'applicazione o in un'altra applicazione  
  
-   Un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class, ad esempio <xref:System.Windows.Forms.Label> o <xref:System.Windows.Forms.TextBox>  
  
-   Un tipo di interfaccia, ad esempio <xref:System.IComparable> o <xref:System.IDisposable>  
  
 È possibile dichiarare più variabili in un'unica istruzione senza dover ripetere il tipo di dati. Nelle istruzioni seguenti, le variabili `i`, `j`, e `k` vengono dichiarati come tipo `Integer`, `l` e `m` come `Long`, e `x` e `y` come `Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Per ulteriori informazioni sui tipi di dati, vedere [tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md). Per ulteriori informazioni sugli oggetti, vedere [oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) e [programmazione con i componenti](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).  
  
## <a name="local-type-inference"></a>Inferenza del tipo di variabile locale  
 *L'inferenza del tipo* viene utilizzata per determinare i tipi di dati delle variabili locali dichiarate senza un `As` clausola. Il compilatore deduce il tipo della variabile dal tipo dell'espressione di inizializzazione. In questo modo è possibile dichiarare variabili senza dichiarare in modo esplicito un tipo. Nell'esempio seguente, entrambi `num1` e `num2` sono fortemente tipizzati come integer.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 Se si desidera usare l'inferenza del tipo locale, `Option Infer` deve essere impostato su `On`. Per altre informazioni, vedere [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferenza del tipo di variabile locale) e [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Istruzione Option Infer).  
  
## <a name="characteristics-of-declared-variables"></a>Caratteristiche di variabili dichiarate  
 Il *durata* di una variabile è il periodo di tempo durante il quale essa è disponibile per l'utilizzo. In generale, esiste una variabile, purché l'elemento che lo dichiara (ad esempio una stored procedure o una classe) continua a esistere. Se la variabile non è necessario continuare esistenti oltre la durata dell'elemento contenitore, non è necessario eseguire alcuna operazione particolare nella dichiarazione. Se la variabile deve continuano a esistere più rispetto all'elemento contenitore, è possibile includere il `Static` o `Shared` (parola chiave) nel relativo `Dim` istruzione. Per ulteriori informazioni, vedere [durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 Il *ambito* di una variabile è il set di tutto il codice che è possibile farvi riferimento senza qualificarne il nome. Ambito di una variabile è determinato in cui è dichiarata. Codice che si trova in una data area può utilizzare le variabili definite in tale area senza dover qualificare i nomi. Per ulteriori informazioni, vedere [ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 Una variabile *livello di accesso* è l'estensione del codice che dispone dell'autorizzazione per accedervi. Ciò è determinato dal modificatore di accesso (ad esempio [pubblica](../../../../visual-basic/language-reference/modifiers/public.md) o [privata](../../../../visual-basic/language-reference/modifiers/private.md)) utilizzato nel `Dim` istruzione. Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Creare una nuova variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)  
 [Procedura: Spostare i dati all'interno e all'esterno di una variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)  
 [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
