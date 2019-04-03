---
title: Tipo di dati di oggetto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 616110145db2796e05509094b1c023daacd68f03
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835570"
---
# <a name="object-data-type"></a>Object Data Type
Contiene gli indirizzi che fanno riferimento a oggetti. È possibile assegnare qualsiasi tipo riferimento (stringa, matrice, classe o interfaccia) a un `Object` variabile. Un' `Object` variabile anche possibile fare riferimento ai dati di qualsiasi tipo di valore (numerico `Boolean`, `Char`, `Date`, struttura o enumerazione).  
  
## <a name="remarks"></a>Note  
 Il `Object` tipo di dati può puntare a dati di qualsiasi tipo di dati, tra cui le istanze di oggetto riconosciuto dall'applicazione. Usare `Object` quando non si conosce in fase di compilazione la variabile di tipo i dati che potrebbe fare riferimento.  
  
 Il valore predefinito `Object` è `Nothing` (un riferimento null).  
  
## <a name="data-types"></a>Tipi di dati  
 È possibile assegnare una variabile, costante o espressione di qualsiasi tipo di dati per un `Object` variabile. Per determinare il tipo di dati un `Object` attualmente fa riferimento alla variabile, è possibile usare il <xref:System.Type.GetTypeCode%2A> metodo il <xref:System.Type?displayProperty=nameWithType> classe. Questa condizione è illustrata nell'esempio seguente.  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 Il `Object` tipo di dati è un tipo riferimento. Tuttavia, Visual Basic considera un `Object` variabile come tipo di valore quando fa riferimento ai dati di un tipo valore.  
  
## <a name="storage"></a>Archiviazione  
 Qualsiasi tipo di dati fa riferimento, un `Object` variabile non contiene il valore di dati stesso, ma piuttosto un puntatore al valore. Usare sempre i quattro byte nella memoria del computer, ma questo non include lo spazio di archiviazione per i dati che rappresenta il valore della variabile. A causa del codice che utilizza il puntatore del mouse per individuare i dati, `Object` variabili che contengono i tipi di valore sono leggermente più lente accedere in modo esplicito rispetto alle variabili di tipo.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di puntatore in altri ambienti non sono compatibili con Visual Basic `Object` tipo.  
  
-   **Prestazioni.** Una variabile dichiarata con la `Object` è sufficientemente flessibile per contenere un riferimento a qualsiasi oggetto di tipo. Tuttavia, quando si richiama un metodo o una proprietà su tale variabile, si verifica sempre *associazione tardiva* (in fase di esecuzione). Per forzare *associazione anticipata* (in fase di compilazione) e ottenere prestazioni migliori, dichiarare la variabile con un nome di classe specifici o eseguirne il cast al tipo di dati specifico.  
  
     Quando si dichiara una variabile oggetto, provare a usare un tipo di classe specifica, ad esempio <xref:System.OperatingSystem>, anziché il generalizzato `Object` tipo. È anche consigliabile utilizzare la classe più specifica disponibile, ad esempio <xref:System.Windows.Forms.TextBox> invece di <xref:System.Windows.Forms.Control>, in modo che è possibile accedere ai relativi metodi e proprietà. In genere, è possibile usare la **classi** nell'elenco il **Visualizzatore oggetti** per trovare i nomi delle classi disponibili.  
  
-   **Widening.** Tutti i tipi di dati e tutti i tipi riferimento ampliano il `Object` tipo di dati. Ciò significa che è possibile convertire qualsiasi tipo a `Object` senza che si verifichi un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
     Tuttavia, se è la conversione tra tipi di valore e `Object`, Visual Basic esegue operazioni chiamate *boxing* e *unboxing*, quale verificare l'esecuzione più lenta.  
  
-   **Caratteri tipo.** `Object` non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la <xref:System.Object?displayProperty=nameWithType> classe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra un `Object` variabile sta puntando a un'istanza dell'oggetto.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Object>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Procedura: Determinare se due oggetti sono correlati](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Procedura: Determinare se due oggetti sono identici](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
