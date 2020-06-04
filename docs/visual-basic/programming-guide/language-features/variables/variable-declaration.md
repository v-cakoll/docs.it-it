---
title: Dichiarazione di variabili
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
ms.openlocfilehash: 587cb84faa09b686361c255c413ad852780b8971
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410296"
---
# <a name="variable-declaration-in-visual-basic"></a>Dichiarazione di variabili in Visual Basic
Viene dichiarata una variabile per specificarne il nome e le caratteristiche. L'istruzione di dichiarazione per le variabili è l' [istruzione Dim](../../../language-reference/statements/dim-statement.md). La posizione e il contenuto determinano le caratteristiche della variabile.  
  
 Per le regole di denominazione delle variabili e le considerazioni, vedere [nomi di elementi dichiarati](../declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Livelli di dichiarazione  
  
### <a name="local-and-member-variables"></a>Variabili locali e membro  
 Una *variabile locale* è una variabile dichiarata all'interno di una routine. Una *variabile membro* è un membro di un tipo di Visual Basic; viene dichiarata a livello di modulo, all'interno di una classe, di una struttura o di un modulo, ma non all'interno di alcuna routine interna alla classe, alla struttura o al modulo.  
  
### <a name="shared-and-instance-variables"></a>Variabili condivise e di istanza  
 In una classe o in una struttura, la categoria di una variabile membro dipende dall'eventuale condivisione o meno. Se viene dichiarata con la parola chiave [Shared](../../../language-reference/modifiers/shared.md) , si tratta di una *variabile condivisa*ed è presente in una singola copia condivisa tra tutte le istanze della classe o della struttura.  
  
 In caso contrario, si tratta di una *variabile di istanza*e ne viene creata una copia separata per ogni istanza della classe o della struttura. Una determinata copia di una variabile di istanza è disponibile solo per l'istanza della classe o della struttura in cui è stata creata. È indipendente da una copia della variabile di istanza in qualsiasi altra istanza della classe o della struttura.  
  
## <a name="declaring-data-type"></a>Dichiarazione del tipo di dati  
 La clausola [As](../../../language-reference/statements/as-clause.md) nell'istruzione Declaration consente di definire il tipo di dati o il tipo di oggetto della variabile che si sta dichiarando. Per una variabile è possibile specificare uno dei tipi seguenti:  
  
- Tipo di dati Elementary, ad esempio `Boolean` , `Long` o`Decimal`  
  
- Tipo di dati composito, ad esempio una matrice o una struttura  
  
- Tipo di oggetto, o classe, definito nell'applicazione o in un'altra applicazione  
  
- Classe .NET Framework, ad esempio <xref:System.Windows.Forms.Label> o<xref:System.Windows.Forms.TextBox>  
  
- Un tipo di interfaccia, ad esempio <xref:System.IComparable> o<xref:System.IDisposable>  
  
 È possibile dichiarare diverse variabili in un'unica istruzione senza dover ripetere il tipo di dati. Nelle istruzioni seguenti le variabili `i` , `j` e `k` vengono dichiarate come tipo e `Integer` `l` come e `m` `Long` `x` e `y` come `Single` :  
  
```vb  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Per ulteriori informazioni sui tipi di dati, vedere [tipi di dati](../data-types/index.md). Per ulteriori informazioni sugli oggetti, vedere [oggetti e classi](../objects-and-classes/index.md) e [programmazione con i componenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).  
  
## <a name="local-type-inference"></a>Inferenza del tipo di variabile locale  
 L' *inferenza del tipo* viene utilizzata per determinare i tipi di dati delle variabili locali dichiarate senza una `As` clausola. Il compilatore deduce il tipo della variabile dal tipo dell'espressione di inizializzazione. Ciò consente di dichiarare le variabili senza indicare esplicitamente un tipo. Nell'esempio seguente, sia `num1` che `num2` sono fortemente tipizzati come numeri interi.  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 Se si desidera utilizzare l'inferenza del tipo locale, `Option Infer` deve essere impostato su `On` . Per altre informazioni, vedere [Local Type Inference](local-type-inference.md) (Inferenza del tipo di variabile locale) e [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) (Istruzione Option Infer).  
  
## <a name="characteristics-of-declared-variables"></a>Caratteristiche delle variabili dichiarate  
 La *durata* di una variabile è il periodo di tempo durante il quale è disponibile per l'utilizzo. In generale, esiste una variabile purché l'elemento che lo dichiara, ad esempio una routine o una classe, continui a esistere. Se non è necessario che la variabile continui a esistere oltre la durata dell'elemento che lo contiene, non è necessario eseguire alcuna operazione speciale nella dichiarazione. Se la variabile deve continuare a esistere più a lungo rispetto all'elemento che lo contiene, è possibile includere la `Static` `Shared` parola chiave o nella relativa `Dim` istruzione. Per ulteriori informazioni, vedere [Lifetime in Visual Basic](../declared-elements/lifetime.md).  
  
 L' *ambito* di una variabile è il set di tutto il codice che può farvi riferimento senza qualificare il nome. L'ambito di una variabile è determinato dalla posizione in cui viene dichiarata. Il codice che si trova in una determinata area può usare le variabili definite in tale area senza che sia necessario qualificarne i nomi. Per altre informazioni, vedere [Scope in Visual Basic](../declared-elements/scope.md).  
  
 Il livello di *accesso* di una variabile è l'ambito del codice che dispone dell'autorizzazione per accedervi. Questa operazione è determinata dal modificatore di accesso (ad esempio [public](../../../language-reference/modifiers/public.md) o [private](../../../language-reference/modifiers/private.md)) usato nell' `Dim` istruzione. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: creare una nuova variabile](how-to-create-a-new-variable.md)
- [Procedura: spostare i dati all'interno e all'esterno di una variabile](how-to-move-data-into-and-out-of-a-variable.md)
- [Tipi di dati](../../../language-reference/data-types/index.md)
- [Protetto](../../../language-reference/modifiers/protected.md)
- [Amico](../../../language-reference/modifiers/friend.md)
- [Statico](../../../language-reference/modifiers/static.md)
- [Caratteristiche di elementi dichiarati](../declared-elements/declared-element-characteristics.md)
- [Inferenza del tipo di variabile locale](local-type-inference.md)
- [Option Infer (istruzione)](../../../language-reference/statements/option-infer-statement.md)
