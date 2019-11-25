---
title: Istruzione ReDim
ms.date: 07/20/2015
f1_keywords:
- vb.ReDim
- vb.Preserve
helpviewer_keywords:
- fixed-length strings [Visual Basic], declaring
- ReDim statement [Visual Basic], syntax
- dynamic arrays [Visual Basic], ReDim statement
- arrays [Visual Basic], reallocating
- arrays [Visual Basic], reinitializing
- arrays [Visual Basic], dimensions
- scalars, and arrays
- scalars
- declarations [Visual Basic], dynamic arrays
- variables [Visual Basic], scalar
- ReDim statement [Visual Basic]
- data types [Visual Basic], assigning
- As keyword [Visual Basic], in ReDim statement
- To keyword [Visual Basic], ReDim statement
- arrays [Visual Basic], declaring
- Preserve keyword [Visual Basic], ReDim statement
- storage [Visual Basic], allocating
- arrays [Visual Basic], and scalars
- declaration statements [Visual Basic]
- scalar variables [Visual Basic]
ms.assetid: ad1c5e07-dcd7-4ae1-a79e-ad3f2dcc2083
ms.openlocfilehash: fabfd9a45d47cc1b881b3743181a03e89158f939
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346743"
---
# <a name="redim-statement-visual-basic"></a>Istruzione ReDim (Visual Basic)
Rialloca lo spazio di archiviazione per una variabile di matrice.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
ReDim [ Preserve ] name(boundlist) [ ,  name(boundlist) [, ... ] ]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|----------|----------------|  
|`Preserve`|Parametro facoltativo. Modificatore utilizzato per conservare i dati nella matrice esistente quando si modifica soltanto la grandezza dell'ultima dimensione.|  
|`name`|Obbligatorio. Nome della variabile di matrice. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`boundlist`|Obbligatorio. Elenco di limiti relativi a ogni dimensione della matrice ridefinita.|  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare l'istruzione `ReDim` per modificare una o più dimensioni di una matrice che è stata già dichiarata. Se si dispone di una matrice di grandi dimensioni e alcuni degli elementi di questa non sono più necessari, `ReDim` consente di liberare memoria riducendo le dimensioni della matrice. D’altra parte, se la matrice necessita di più elementi, `ReDim` è in grado di aggiungerli.  
  
 L'istruzione `ReDim` è destinata solo alle matrici. Non è valida per valori scalari (variabili che contengono un unico valore), raccolte o strutture. Tenere presente che se l'utente dichiara che una variabile è di tipo `Array`, l'istruzione `ReDim` non dispone di sufficienti informazioni sulla tipologia e non può creare la nuova matrice.  
  
 Si può usare `ReDim` solo a livello di routine. Pertanto, il contesto della dichiarazione relativo alla variabile deve essere una routine. Di conseguenza, non può essere un file di origine, uno spazio dei nomi, un'interfaccia, una classe, una struttura, un modulo o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
## <a name="rules"></a>Regole  
  
- **Multiple Variables.** You can resize several array variables in the same declaration statement and specify the `name` and `boundlist` parts for each variable. Nel caso di più variabili, è possibile separarle mediante virgole.  
  
- **Array Bounds.** Each entry in `boundlist` can specify the lower and upper bounds of that dimension. Il limite inferiore è sempre pari a 0 (zero). Il limite superiore rappresenta il valore di indice più alto possibile per la dimensione, non la lunghezza della dimensione (vale a dire, il limite superiore più uno). L'indice di ogni dimensione può variare tra 0 e il relativo valore di limite superiore.  
  
     Il numero di dimensioni in `boundlist` deve corrispondere al numero originale di dimensioni (livello) della matrice.  
  
- **Data Types.** The `ReDim` statement cannot change the data type of an array variable or its elements.  
  
- **Initialization.** The `ReDim` statement cannot provide new initialization values for the array elements.  
  
- **Rank.** The `ReDim` statement cannot change the rank (the number of dimensions) of the array.  
  
- **Resizing with Preserve.** If you use `Preserve`, you can resize only the last dimension of the array. Per ogni dimensione, è necessario specificare il limite della matrice esistente.  
  
     Ad esempio, se la matrice contiene solo una dimensione, è possibile ridimensionarla e mantenere tutto il contenuto della matrice, poiché si sta modificando l'ultima e unica dimensione. Tuttavia, se la matrice dispone di due o più dimensioni e si utilizza `Preserve`, è possibile modificare i valori soltanto per l'ultima dimensione.  
  
- **Properties.** You can use `ReDim` on a property that holds an array of values.  
  
## <a name="behavior"></a>Comportamento  
  
- **Array Replacement.** `ReDim` releases the existing array and creates a new array with the same rank. La nuova matrice sostituisce quella rilasciata nella variabile di matrice.  
  
- **Initialization without Preserve.** If you do not specify `Preserve`, `ReDim` initializes the elements of the new array by using the default value for their data type.  
  
- **Initialization with Preserve.** If you specify `Preserve`, Visual Basic copies the elements from the existing array to the new array.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene aumentata la grandezza dell'ultima dimensione di una matrice dinamica senza perdere i dati presenti nella matrice; in seguito, viene ridotta la dimensione con perdita di dati parziali. Infine, viene ridotta la dimensione del relativo valore originale e vengono inizializzati di nuovo tutti gli elementi della matrice.  
  
 [!code-vb[VbVbalrStatements#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#52)]  
  
 L'istruzione `Dim` crea una nuova matrice con tre dimensioni. Ogni dimensione viene dichiarata con un limite pari a 10. In questo modo l'indice della matrice per ogni dimensione può essere compreso tra 0 e 10. Nella seguente discussione, si fa riferimento alle tre dimensioni come livello, riga e colonna.  
  
 La prima `ReDim` crea una nuova matrice che sostituisce quella esistente nella `intArray` di variabile. `ReDim` copia tutti gli elementi dalla matrice esistente in quella nuova. Inoltre, consente di aggiungere altre 10 colonne alla fine di ogni riga di tutti i livelli e consente di inizializzare gli elementi in queste nuove colonne su 0 (valore predefinito) di `Integer`, ovvero il tipo di elemento della matrice.  
  
 La seconda `ReDim` crea una nuova matrice e copia tutti gli elementi adeguati. Tuttavia, cinque colonne vengono perse alla fine di ogni riga relativa a ogni livello. Ciò non rappresenta un problema se l'utente non ha più la necessità di utilizzare tali colonne. La riduzione delle dimensioni di una grande matrice può liberare memoria che non è più necessaria.  
  
 La terza `ReDim` crea una nuova matrice e rimuove altre cinque colonne dalla fine di ogni riga relativa a ogni livello. Questa volta non copia gli elementi esistenti. Questa istruzione consente di ripristinare le dimensioni originali della matrice. Dal momento che l'istruzione non include il modificatore `Preserve`, imposta i valori predefiniti originali di tutti gli elementi della matrice.  
  
 For additional examples, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IndexOutOfRangeException>
- [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Istruzione Erase](../../../visual-basic/language-reference/statements/erase-statement.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [Array](../../../visual-basic/programming-guide/language-features/arrays/index.md)
