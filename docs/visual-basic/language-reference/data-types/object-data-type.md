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
ms.openlocfilehash: 14770e74a0169dba3a45a04845dd32323e6201e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415583"
---
# <a name="object-data-type"></a>Object Data Type

Include indirizzi che fanno riferimento a oggetti. È possibile assegnare qualsiasi tipo di riferimento (stringa, matrice, classe o interfaccia) a una `Object` variabile. Una `Object` variabile può anche fare riferimento a dati di qualsiasi tipo di valore (numeric,,,, `Boolean` `Char` `Date` Structure o Enumeration).

## <a name="remarks"></a>Commenti

Il `Object` tipo di dati può puntare a dati di qualsiasi tipo di dati, inclusa qualsiasi istanza di oggetto riconosciuta dall'applicazione. Usare `Object` quando non si conosce in fase di compilazione a quale tipo di dati può puntare la variabile.

Il valore predefinito di `Object` è `Nothing` (un riferimento null).

## <a name="data-types"></a>Tipi di dati

È possibile assegnare una variabile, una costante o un'espressione di qualsiasi tipo di dati a una `Object` variabile. Per determinare il tipo di dati `Object` a cui fa attualmente riferimento una variabile, è possibile usare il <xref:System.Type.GetTypeCode%2A> metodo della <xref:System.Type?displayProperty=nameWithType> classe. Questa condizione è illustrata nell'esempio seguente.

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

Il `Object` tipo di dati è un tipo di riferimento. Tuttavia, Visual Basic considera una `Object` variabile come tipo di valore quando fa riferimento ai dati di un tipo di valore.

## <a name="storage"></a>Archiviazione

Indipendentemente dal tipo di dati a cui fa riferimento, una `Object` variabile non contiene il valore di dati stesso, bensì un puntatore al valore. Usa sempre quattro byte nella memoria del computer, ma non include l'archiviazione per i dati che rappresentano il valore della variabile. A causa del codice che usa il puntatore per individuare i dati, le `Object` variabili che mantengono i tipi di valore sono leggermente più lente per accedere alle variabili tipizzate in modo esplicito.

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Considerazioni sull'interoperabilità.** Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di puntatore in altri ambienti non sono compatibili con il `Object` tipo di Visual Basic.

- **Prestazioni.** Una variabile dichiarata con il `Object` tipo è sufficientemente flessibile da contenere un riferimento a qualsiasi oggetto. Tuttavia, quando si richiama un metodo o una proprietà in una variabile di questo tipo, si verifica sempre un' *associazione tardiva* (in fase di esecuzione). Per forzare l' *associazione anticipata* (in fase di compilazione) e migliorare le prestazioni, dichiarare la variabile con un nome di classe specifico oppure eseguirne il cast al tipo di dati specifico.

  Quando si dichiara una variabile oggetto, provare a usare un tipo di classe specifico, ad esempio <xref:System.OperatingSystem> , anziché il tipo generalizzato `Object` . È inoltre consigliabile utilizzare la classe più specifica disponibile, ad esempio <xref:System.Windows.Forms.TextBox> anziché <xref:System.Windows.Forms.Control> , in modo da poter accedere alle proprietà e ai metodi. In genere, è possibile usare l'elenco delle **classi** nella **Visualizzatore oggetti** per trovare i nomi delle classi disponibili.

- **Conversioni.** Tutti i tipi di dati e tutti i tipi di riferimento vengono ampliati al `Object` tipo di dati. Ciò significa che è possibile convertire qualsiasi tipo in `Object` senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.

  Tuttavia, se si esegue la conversione tra tipi di valore e `Object` , Visual Basic esegue operazioni *unboxing*denominate *Boxing* e unboxing, che rendono l'esecuzione più lenta.

- **Digitare i caratteri.** `Object`non ha un carattere di tipo letterale o un carattere di tipo identificatore.

- **Tipo di framework.** Il tipo corrispondente nella .NET Framework è la <xref:System.Object?displayProperty=nameWithType> classe.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata una `Object` variabile che punta a un'istanza dell'oggetto.

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Object>
- [Tipi di dati](index.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Procedura: determinare se due oggetti sono correlati](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Procedura: determinare se due oggetti sono identici](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
