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
ms.openlocfilehash: 4706f306e8db252b35148f8e6a0f8c42122f5482
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583385"
---
# <a name="variable-declaration-in-visual-basic"></a>Dichiarazione di variabili in Visual Basic
Si dichiara una variabile per specificare il nome e le caratteristiche. Istruzione di dichiarazione delle variabili è il [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). La posizione e il contenuto determinano le caratteristiche della variabile.  
  
 Per le regole di denominazione variabile e considerazioni, vedere [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Livelli di dichiarazione  
  
### <a name="local-and-member-variables"></a>Locale e le variabili membro  
 Oggetto *variabile locale* è una variabile dichiarata all'interno di una routine. Oggetto *variabile membro* è un membro di un tipo di Visual Basic; è dichiarato a livello di modulo, all'interno di una classe, struttura o modulo, ma non all'interno di qualsiasi routine interne di tale classe, struttura o modulo.  
  
### <a name="shared-and-instance-variables"></a>Condiviso e le variabili di istanze  
 In una classe o struttura, la categoria di una variabile membro dipende o meno è condivisa. Se è dichiarata con la [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) parola chiave, è un *variabile condivisa*, e l'indice esiste in una sola copia condivisa tra tutte le istanze della classe o struttura.  
  
 In caso contrario, è un' *variabile di istanza*, e viene creata una copia separata per ogni istanza della classe o struttura. È disponibile solo per l'istanza della classe o struttura in cui è stata creata una copia specifica di una variabile di istanza. È indipendente da una copia della variabile di istanza in qualsiasi altra istanza della classe o struttura.  
  
## <a name="declaring-data-type"></a>La dichiarazione di tipo di dati  
 Il [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola nell'istruzione di dichiarazione consente di definire il tipo di dati o un tipo di oggetto della variabile che si sta dichiarando. È possibile specificare uno dei seguenti tipi per una variabile:  
  
- Digitare un dati elementari, ad esempio `Boolean`, `Long`, o `Decimal`  
  
- Un tipo di dati composta, ad esempio una matrice o una struttura  
  
- Un tipo di oggetto o classe, definito nell'applicazione o in un'altra applicazione  
  
- Classe di .NET Framework, ad esempio <xref:System.Windows.Forms.Label> o <xref:System.Windows.Forms.TextBox>  
  
- Tipo di un'interfaccia, ad esempio <xref:System.IComparable> o <xref:System.IDisposable>  
  
 È possibile dichiarare più variabili in un'unica istruzione senza dover ripetere il tipo di dati. Nelle istruzioni seguenti, le variabili `i`, `j`, e `k` vengono dichiarati come tipo `Integer`, `l` e `m` come `Long`, e `x` e `y` come `Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Per altre informazioni sui tipi di dati, vedere [tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md). Per altre informazioni sugli oggetti, vedere [oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) e [programmazione con i componenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).  
  
## <a name="local-type-inference"></a>Inferenza del tipo di variabile locale  
 *L'inferenza del tipo* viene usato per determinare i tipi di dati delle variabili locali dichiarate senza un `As` clausola. Il compilatore deduce il tipo della variabile dal tipo dell'espressione di inizializzazione. In questo modo è possibile dichiarare le variabili senza specificare esplicitamente un tipo. Nell'esempio seguente, entrambe `num1` e `num2` sono fortemente tipizzati come numeri interi.  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 Se si desidera usare l'inferenza del tipo locale, `Option Infer` deve essere impostata su `On`. Per altre informazioni, vedere [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferenza del tipo di variabile locale) e [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Istruzione Option Infer).  
  
## <a name="characteristics-of-declared-variables"></a>Caratteristiche delle variabili dichiarate  
 Il *durata* di una variabile è il periodo di tempo durante cui si è disponibile per l'uso. In generale, esiste una variabile, purché l'elemento che lo dichiara (ad esempio, una procedura o una classe) continua a esistere. Se la variabile non è necessario continuare esistenti oltre la durata del relativo elemento contenitore, non devi eseguire alcuna operazione speciale nella dichiarazione. Se la variabile deve continuare a esistere più rispetto all'elemento contenitore, è possibile includere il `Static` oppure `Shared` parola chiave nel relativo `Dim` istruzione. Per altre informazioni, vedere [durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 Il *ambito* è il set di tutto il codice che può fare riferimento ad esso senza qualificare il nome di una variabile. Ambito di una variabile è determinato da dove è dichiarato. Codice che si trova in una determinata area è possibile usare le variabili definite in tale area senza dover qualificare i relativi nomi. Per altre informazioni, vedere [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 Una variabile *livello di accesso* è l'estensione di codice che dispone dell'autorizzazione per accedervi. Ciò è determinato dal modificatore di accesso (ad esempio [pubblico](../../../../visual-basic/language-reference/modifiers/public.md) o [privato](../../../../visual-basic/language-reference/modifiers/private.md)) utilizzabili nel `Dim` istruzione. Per altre informazioni, vedere [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare una nuova variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)
- [Procedura: Spostare dati da e verso una variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)
- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
- [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
- [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
