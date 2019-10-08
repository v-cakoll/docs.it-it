---
title: Dichiarazione di variabili in Visual Basic
ms.date: 07/20/2015
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
ms.openlocfilehash: 726347efc2e12100f7d89348a316037babc785e5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003293"
---
# <a name="variable-declaration-in-visual-basic"></a>Dichiarazione di variabili in Visual Basic
Viene dichiarata una variabile per specificarne il nome e le caratteristiche. L'istruzione di dichiarazione per le variabili è l' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). La posizione e il contenuto determinano le caratteristiche della variabile.  
  
 Per le regole di denominazione delle variabili e le considerazioni, vedere [nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Livelli di dichiarazione  
  
### <a name="local-and-member-variables"></a>Variabili locali e membro  
 Una *variabile locale* è una variabile dichiarata all'interno di una routine. Una *variabile membro* è un membro di un tipo di Visual Basic; viene dichiarata a livello di modulo, all'interno di una classe, di una struttura o di un modulo, ma non all'interno di alcuna routine interna alla classe, alla struttura o al modulo.  
  
### <a name="shared-and-instance-variables"></a>Variabili condivise e di istanza  
 In una classe o in una struttura, la categoria di una variabile membro dipende dall'eventuale condivisione o meno. Se viene dichiarata con la parola chiave [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) , si tratta di una *variabile condivisa*ed è presente in una singola copia condivisa tra tutte le istanze della classe o della struttura.  
  
 In caso contrario, si tratta di una *variabile di istanza*e ne viene creata una copia separata per ogni istanza della classe o della struttura. Una determinata copia di una variabile di istanza è disponibile solo per l'istanza della classe o della struttura in cui è stata creata. È indipendente da una copia della variabile di istanza in qualsiasi altra istanza della classe o della struttura.  
  
## <a name="declaring-data-type"></a>Dichiarazione del tipo di dati  
 La clausola [As](../../../../visual-basic/language-reference/statements/as-clause.md) nell'istruzione Declaration consente di definire il tipo di dati o il tipo di oggetto della variabile che si sta dichiarando. Per una variabile è possibile specificare uno dei tipi seguenti:  
  
- Tipo di dati Elementary, ad esempio `Boolean`, `Long` o `Decimal`  
  
- Tipo di dati composito, ad esempio una matrice o una struttura  
  
- Tipo di oggetto, o classe, definito nell'applicazione o in un'altra applicazione  
  
- Classe .NET Framework, ad esempio <xref:System.Windows.Forms.Label> o <xref:System.Windows.Forms.TextBox>  
  
- Tipo di interfaccia, ad esempio <xref:System.IComparable> o <xref:System.IDisposable>  
  
 È possibile dichiarare diverse variabili in un'unica istruzione senza dover ripetere il tipo di dati. Nelle istruzioni seguenti le variabili `i`, `j` e `k` sono dichiarate come tipo `Integer`, `l` e `m` come `Long` e `x` e `y` come `Single`:  
  
```vb  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Per ulteriori informazioni sui tipi di dati, vedere [tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md). Per ulteriori informazioni sugli oggetti, vedere [oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) e [programmazione con i componenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).  
  
## <a name="local-type-inference"></a>Inferenza del tipo di variabile locale  
 L' *inferenza del tipo* viene utilizzata per determinare i tipi di dati delle variabili locali dichiarate senza una clausola `As`. Il compilatore deduce il tipo della variabile dal tipo dell'espressione di inizializzazione. Ciò consente di dichiarare le variabili senza indicare esplicitamente un tipo. Nell'esempio seguente, entrambi `num1` e `num2` sono fortemente tipizzati come numeri interi.  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 Se si desidera utilizzare l'inferenza del tipo locale, `Option Infer` deve essere impostato su `On`. Per altre informazioni, vedere [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferenza del tipo di variabile locale) e [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Istruzione Option Infer).  
  
## <a name="characteristics-of-declared-variables"></a>Caratteristiche delle variabili dichiarate  
 La *durata* di una variabile è il periodo di tempo durante il quale è disponibile per l'utilizzo. In generale, esiste una variabile purché l'elemento che lo dichiara, ad esempio una routine o una classe, continui a esistere. Se non è necessario che la variabile continui a esistere oltre la durata dell'elemento che lo contiene, non è necessario eseguire alcuna operazione speciale nella dichiarazione. Se la variabile deve continuare a esistere più a lungo rispetto all'elemento che lo contiene, è possibile includere la parola chiave `Static` o `Shared` nell'istruzione `Dim`. Per ulteriori informazioni, vedere [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 L' *ambito* di una variabile è il set di tutto il codice che può farvi riferimento senza qualificare il nome. L'ambito di una variabile è determinato dalla posizione in cui viene dichiarata. Il codice che si trova in una determinata area può usare le variabili definite in tale area senza che sia necessario qualificarne i nomi. Per altre informazioni, vedere [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 Il livello di *accesso* di una variabile è l'ambito del codice che dispone dell'autorizzazione per accedervi. Questo è determinato dal modificatore di accesso (ad esempio [public](../../../../visual-basic/language-reference/modifiers/public.md) o [private](../../../../visual-basic/language-reference/modifiers/private.md)) usato nell'istruzione `Dim`. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Crea una nuova variabile @ no__t-0
- [Procedura: Spostare i dati all'interno e all'esterno di una variabile @ no__t-0
- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
- [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
- [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
