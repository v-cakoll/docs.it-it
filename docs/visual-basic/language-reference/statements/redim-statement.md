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
ms.openlocfilehash: 82f19762865fdf3c3f32a0349e21e3b97bebd567
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404278"
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
|`Preserve`|Facoltativa. Modificatore utilizzato per conservare i dati nella matrice esistente quando si modifica soltanto la grandezza dell'ultima dimensione.|  
|`name`|Obbligatorio. Nome della variabile di matrice. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`boundlist`|Obbligatorio. Elenco di limiti relativi a ogni dimensione della matrice ridefinita.|  
  
## <a name="remarks"></a>Commenti  
 È possibile utilizzare l'istruzione `ReDim` per modificare una o più dimensioni di una matrice che è stata già dichiarata. Se si dispone di una matrice di grandi dimensioni e alcuni degli elementi di questa non sono più necessari, `ReDim` consente di liberare memoria riducendo le dimensioni della matrice. D’altra parte, se la matrice necessita di più elementi, `ReDim` è in grado di aggiungerli.  
  
 L'istruzione `ReDim` è destinata solo alle matrici. Non è valida per valori scalari (variabili che contengono un unico valore), raccolte o strutture. Tenere presente che se l'utente dichiara che una variabile è di tipo `Array`, l'istruzione `ReDim` non dispone di sufficienti informazioni sulla tipologia e non può creare la nuova matrice.  
  
 Si può usare `ReDim` solo a livello di routine. Pertanto, il contesto della dichiarazione relativo alla variabile deve essere una routine. Di conseguenza, non può essere un file di origine, uno spazio dei nomi, un'interfaccia, una classe, una struttura, un modulo o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).  
  
## <a name="rules"></a>Regole  
  
- **Variabili multiple.** È possibile ridimensionare diverse variabili di matrice nella stessa istruzione di dichiarazione e specificare le `name` `boundlist` parti e per ogni variabile. Nel caso di più variabili, è possibile separarle mediante virgole.  
  
- **Limiti della matrice.** Ogni voce in `boundlist` può specificare i limiti inferiore e superiore della dimensione. Il limite inferiore è sempre pari a 0 (zero). Il limite superiore rappresenta il valore di indice più alto possibile per la dimensione, non la lunghezza della dimensione (vale a dire, il limite superiore più uno). L'indice di ogni dimensione può variare tra 0 e il relativo valore di limite superiore.  
  
     Il numero di dimensioni in `boundlist` deve corrispondere al numero originale di dimensioni (livello) della matrice.  
  
- **Tipi di dati.** L' `ReDim` istruzione non può modificare il tipo di dati di una variabile di matrice o dei relativi elementi.  
  
- **Inizializzazione.** L' `ReDim` istruzione non può fornire nuovi valori di inizializzazione per gli elementi della matrice.  
  
- **Rank.** L' `ReDim` istruzione non può modificare il rango (numero di dimensioni) della matrice.  
  
- **Ridimensionamento con Preserve.** Se si utilizza `Preserve` , è possibile ridimensionare solo l'ultima dimensione della matrice. Per ogni dimensione, è necessario specificare il limite della matrice esistente.  
  
     Ad esempio, se la matrice contiene solo una dimensione, è possibile ridimensionarla e mantenere tutto il contenuto della matrice, poiché si sta modificando l'ultima e unica dimensione. Tuttavia, se la matrice dispone di due o più dimensioni e si utilizza `Preserve`, è possibile modificare i valori soltanto per l'ultima dimensione.  
  
- **Proprietà.** È possibile utilizzare `ReDim` su una proprietà che include una matrice di valori.  
  
## <a name="behavior"></a>Comportamento  
  
- **Sostituzione di matrici.** `ReDim`rilascia la matrice esistente e crea una nuova matrice con lo stesso rango. La nuova matrice sostituisce quella rilasciata nella variabile di matrice.  
  
- **Inizializzazione senza Preserve.** Se non si specifica `Preserve` , `ReDim` Inizializza gli elementi della nuova matrice usando il valore predefinito per il tipo di dati.  
  
- **Inizializzazione con Preserve.** Se si specifica `Preserve` , Visual Basic copia gli elementi dalla matrice esistente alla nuova matrice.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene aumentata la grandezza dell'ultima dimensione di una matrice dinamica senza perdere i dati presenti nella matrice; in seguito, viene ridotta la dimensione con perdita di dati parziali. Infine, viene ridotta la dimensione del relativo valore originale e vengono inizializzati di nuovo tutti gli elementi della matrice.  
  
 [!code-vb[VbVbalrStatements#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#52)]  
  
 L'istruzione `Dim` crea una nuova matrice con tre dimensioni. Ogni dimensione viene dichiarata con un limite pari a 10. In questo modo l'indice della matrice per ogni dimensione può essere compreso tra 0 e 10. Nella seguente discussione, si fa riferimento alle tre dimensioni come livello, riga e colonna.  
  
 La prima `ReDim` crea una nuova matrice che sostituisce quella esistente nella `intArray` di variabile. `ReDim` copia tutti gli elementi dalla matrice esistente in quella nuova. Inoltre, consente di aggiungere altre 10 colonne alla fine di ogni riga di tutti i livelli e consente di inizializzare gli elementi in queste nuove colonne su 0 (valore predefinito) di `Integer`, ovvero il tipo di elemento della matrice.  
  
 La seconda `ReDim` crea una nuova matrice e copia tutti gli elementi adeguati. Tuttavia, cinque colonne vengono perse alla fine di ogni riga relativa a ogni livello. Ciò non rappresenta un problema se l'utente non ha più la necessità di utilizzare tali colonne. La riduzione delle dimensioni di una grande matrice può liberare memoria che non è più necessaria.  
  
 La terza `ReDim` crea una nuova matrice e rimuove altre cinque colonne dalla fine di ogni riga relativa a ogni livello. Questa volta non copia gli elementi esistenti. Questa istruzione consente di ripristinare le dimensioni originali della matrice. Dal momento che l'istruzione non include il modificatore `Preserve`, imposta i valori predefiniti originali di tutti gli elementi della matrice.  
  
 Per altri esempi, vedere [matrici](../../programming-guide/language-features/arrays/index.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IndexOutOfRangeException>
- [Istruzione Const](const-statement.md)
- [Istruzione Dim](dim-statement.md)
- [Istruzione Erase](erase-statement.md)
- [Nothing](../nothing.md)
- [Matrici](../../programming-guide/language-features/arrays/index.md)
