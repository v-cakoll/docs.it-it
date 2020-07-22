---
title: Passaggio di parametri di tipo di riferimento - Guida per programmatori C#
description: Quando si passa un parametro di tipo riferimento per valore in C#, i dati nell'oggetto a cui si fa riferimento possono cambiare, ma non il valore del riferimento stesso.
ms.date: 07/20/2015
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
ms.openlocfilehash: 64a4735eded7a468549862b3221b4fbd0966e64d
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864709"
---
# <a name="passing-reference-type-parameters-c-programming-guide"></a>Passaggio di parametri di tipo di riferimento (Guida per programmatori C#)
Una variabile di un [tipo riferimento](../../language-reference/keywords/reference-types.md) non contiene direttamente i dati, ma solo un riferimento a essi. Quando si passa un parametro di tipo riferimento per valore, è possibile modificare i dati appartenenti all'oggetto di riferimento, ad esempio il valore del membro di una classe. Non è tuttavia possibile modificare il valore del riferimento stesso. Ad esempio, non è possibile usare lo stesso riferimento per allocare memoria per un nuovo oggetto e per renderlo persistente all'esterno del metodo. In questo caso, è necessario passare il parametro usando la parola chiave [ref](../../language-reference/keywords/ref.md) o [out](../../language-reference/keywords/out-parameter-modifier.md). Per semplicità, negli esempi seguenti viene usato `ref`.  
  
## <a name="passing-reference-types-by-value"></a>Passaggio di tipi riferimento per valore  
 Nell'esempio seguente viene illustrato il passaggio per valore di un parametro di tipo riferimento, `arr`, a un metodo, `Change`. Poiché il parametro è un riferimento a `arr`, è possibile modificare i valori degli elementi della matrice. Il tentativo di riassegnare il parametro a una diversa posizione in memoria, tuttavia, è efficace solo all'interno del metodo e non ha alcun effetto sulla variabile originale `arr`.  
  
 [!code-csharp[csProgGuideParameters#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#7)]  
  
 Nell'esempio precedente, la matrice `arr`, che rappresenta un tipo riferimento, viene passata al metodo senza il parametro `ref`. In questo caso, al metodo viene passata una copia del riferimento che punta a `arr`. L'output indica che il metodo ha la possibilità di modificare il contenuto di un elemento della matrice (da `1` a `888`). L'allocazione di una nuova porzione di memoria usando l'operatore [new](../../language-reference/operators/new-operator.md) nel metodo `Change`, tuttavia, fa sì che la variabile `pArray` faccia riferimento a una nuova matrice. In questo modo, eventuali modifiche successive non avranno effetto sulla matrice originale `arr`, creata in `Main`. In realtà, in questo esempio vengono create due matrici: una in `Main` e una nel metodo `Change`.  
  
## <a name="passing-reference-types-by-reference"></a>Passaggio di tipi riferimento per riferimento  
 L'esempio seguente è identico a quello precedente, tranne per il fatto che la parola chiave `ref` viene aggiunta all'intestazione e alla chiamata del metodo. Tutte le modifiche apportate nel metodo si ripercuotono sulla variabile originale nel programma chiamante.  
  
 [!code-csharp[csProgGuideParameters#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#8)]  
  
 Tutte le modifiche apportate all'interno del metodo si ripercuotono sulla variabile originale in `Main`. In realtà, la matrice originale viene riallocata mediante l'operatore `new`. Dopo la chiamata al metodo `Change`, quindi, i riferimenti a `arr` puntano alla matrice a cinque elementi creata nel metodo `Change`.  
  
## <a name="swapping-two-strings"></a>Scambio di due stringhe  
 Lo scambio di stringhe è un buon esempio per illustrare il passaggio per riferimento di parametri di tipo riferimento. In questo esempio, due stringhe, `str1` e `str2`, vengono inizializzate in `Main` e passate al metodo `SwapStrings` come parametri modificati dalla parola chiave `ref`. Le due stringhe vengono scambiate all'interno del metodo e all'interno di `Main`.  
  
 [!code-csharp[csProgGuideParameters#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#9)]  
  
 In questo esempio è necessario passare i parametri per riferimento perché abbiano effetto sulle variabili del programma chiamante. Se si rimuove la parola chiave `ref` sia dall'intestazione del metodo che dalla chiamata al metodo, nel programma chiamante non avrà luogo alcuna modifica.  
  
 Per altre informazioni sulle stringhe, vedere [Stringhe](../../language-reference/builtin-types/reference-types.md).  
  
## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../index.md)
- [Passaggio di parametri](./passing-parameters.md)
- [ref](../../language-reference/keywords/ref.md)
- [in](../../language-reference/keywords/in-parameter-modifier.md)
- [out](../../language-reference/keywords/out.md)
- [Tipi di riferimento](../../language-reference/keywords/reference-types.md)
