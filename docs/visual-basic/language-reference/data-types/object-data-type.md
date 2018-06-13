---
title: Object Data Type
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
ms.openlocfilehash: e9b1da5a88c12e0d883c3afe63be98c3fa3e9173
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591625"
---
# <a name="object-data-type"></a>Object Data Type
Contiene gli indirizzi che fanno riferimento a oggetti. È possibile assegnare qualsiasi tipo riferimento (stringa, matrice, classe o interfaccia) a un `Object` variabile. Un `Object` variabile può inoltre fare riferimento ai dati di qualsiasi tipo di valore (numerico, `Boolean`, `Char`, `Date`, struttura o enumerazione).  
  
## <a name="remarks"></a>Note  
 Il `Object` tipo di dati può fare riferimento ai dati di qualsiasi tipo di dati, inclusi qualsiasi istanza dell'oggetto riconosciuto dall'applicazione. Utilizzare `Object` quando non si conosce in fase di compilazione può scegliere il tipo di dati la variabile.  
  
 Il valore predefinito di `Object` è `Nothing` (un riferimento null).  
  
## <a name="data-types"></a>Tipi di dati  
 È possibile assegnare una variabile, costante o espressione di qualsiasi tipo di dati per un `Object` variabile. Per determinare il tipo di dati un `Object` variabile fa attualmente riferimento a, è possibile utilizzare il <xref:System.Type.GetTypeCode%2A> metodo la <xref:System.Type?displayProperty=nameWithType> classe. Questa condizione è illustrata nell'esempio seguente.  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 Il `Object` tipo di dati è un tipo di riferimento. Tuttavia, Visual Basic considera un `Object` variabile come tipo di valore quando fa riferimento a un tipo di valore.  
  
## <a name="storage"></a>Archiviazione  
 Indipendentemente dal tipo di dati fa riferimento a un `Object` variabile non contiene il valore dati stesso, mentre un puntatore al valore. Utilizza sempre quattro byte nella memoria del computer, ma non include lo spazio di archiviazione per i dati che rappresenta il valore della variabile. A causa di codice che utilizza l'indicatore di misura per individuare i dati, `Object` variabili che contengono i tipi di valore sono leggermente più lente accedere a in modo esplicito le variabili tipizzate.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di puntatore in altri ambienti non sono compatibili con Visual Basic `Object` tipo.  
  
-   **Prestazioni.** Una variabile dichiarata con la `Object` tipo è sufficientemente flessibile per contenere un riferimento a qualsiasi oggetto. Tuttavia, quando si richiama un metodo o una proprietà di queste variabili, si verifica sempre *ad associazione tardiva* (in fase di esecuzione). Per forzare *associazione anticipata* (in fase di compilazione) e prestazioni migliori, dichiarare la variabile con un nome di classe specifico o eseguirne il cast al tipo di dati specifico.  
  
     Quando si dichiara una variabile oggetto, provare a utilizzare un tipo di classe specifici, ad esempio <xref:System.OperatingSystem>, anziché il generalizzato `Object` tipo. È inoltre necessario utilizzare la classe più specifica disponibile, ad esempio <xref:System.Windows.Forms.TextBox> anziché <xref:System.Windows.Forms.Control>, in modo che i relativi metodi e proprietà, è possibile accedere. In genere, è possibile utilizzare il **classi** nell'elenco di **Visualizzatore oggetti** per trovare i nomi delle classi disponibili.  
  
-   **Ampliamento.** Tutti i tipi di dati e tutti i tipi di riferimento vengono ampliati al `Object` tipo di dati. È pertanto possibile convertire qualsiasi tipo per `Object` senza che si verifichi un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
     Tuttavia, se è la conversione tra tipi di valore e `Object`, Visual Basic esegue le operazioni di *boxing* e *unboxing*, che rendono l'esecuzione più lenta.  
  
-   **Caratteri tipo.** `Object` non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la <xref:System.Object?displayProperty=nameWithType> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un `Object` variabile che punta a un'istanza dell'oggetto.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Object>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Procedura: determinare se due oggetti sono correlati](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Procedura: determinare se due oggetti sono identici](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
