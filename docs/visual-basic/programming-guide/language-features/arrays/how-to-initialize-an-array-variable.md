---
title: 'Procedura: Inizializzare una variabile di matrice'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: 7feaf71fa1c59c24aa751f2b9e28328d47ba357c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413066"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a>Procedura: inizializzare una variabile di matrice in Visual Basic
Per inizializzare una variabile di matrice, è necessario includere un valore letterale di matrice in una `New` clausola e specificare i valori iniziali della matrice. È possibile specificare il tipo o consentirne la deduzione dai valori nel valore letterale di matrice. Per ulteriori informazioni sul modo in cui il tipo viene dedotto, vedere "popolamento di una matrice con valori iniziali" nelle [matrici](index.md).  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a>Per inizializzare una variabile di matrice utilizzando un valore letterale di matrice  
  
- Nella `New` clausola o quando si assegna il valore della matrice, fornire i valori dell'elemento racchiusi tra parentesi graffe ( `{}` ). Nell'esempio seguente vengono illustrati diversi modi per dichiarare, creare e inizializzare una variabile in modo che contenga una matrice con elementi di tipo `Char` .  
  
     [!code-vb[VbVbalrArrays#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#16)]  
  
     Dopo l'esecuzione di ogni istruzione, la matrice creata ha una lunghezza di 3, con elementi in corrispondenza dell'indice 0 fino all'indice 2 che contiene i valori iniziali. Se si specificano sia il limite superiore che i valori, è necessario includere un valore per ogni elemento dall'indice 0 al limite superiore.  
  
     Si noti che non è necessario specificare il limite superiore dell'indice se si forniscono i valori degli elementi in un valore letterale di matrice. Se non viene specificato alcun limite superiore, le dimensioni della matrice vengono dedotte in base al numero di valori nel valore letterale di matrice.  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a>Per inizializzare una variabile di matrice multidimensionale tramite valori letterali di matrice  
  
- Annidare i valori racchiusi tra parentesi graffe ( `{}` ) racchiusi tra parentesi graffe. Assicurarsi che i valori letterali di matrice annidati deducano tutti come matrici dello stesso tipo e della stessa lunghezza. Nell'esempio di codice seguente vengono illustrati diversi esempi di inizializzazione di matrici multidimensionali.  
  
     [!code-vb[VbVbalrArrays#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#17)]  
  
- È possibile specificare in modo esplicito i limiti della matrice oppure ometterli e fare in modo che il compilatore deduca i limiti della matrice in base ai valori nel valore letterale di matrice. Se si forniscono sia i limiti superiori che i valori, è necessario includere un valore per ogni elemento dall'indice 0 al limite superiore in ogni dimensione. Nell'esempio seguente vengono illustrati diversi modi per dichiarare, creare e inizializzare una variabile in modo che contenga una matrice bidimensionale con elementi di tipo`Short`  
  
     [!code-vb[VbVbalrArrays#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#18)]  
  
     Dopo l'esecuzione di ogni istruzione, la matrice creata contiene sei elementi inizializzati con indici,,,, `(0,0)` `(0,1)` `(0,2)` `(1,0)` `(1,1)` e `(1,2)` . Ogni posizione della matrice contiene il valore `10` .  
  
- Nell'esempio seguente viene eseguita l'iterazione di una matrice multidimensionale. In un'applicazione console di Windows scritta in Visual Basic, incollare il codice all'interno del `Sub Main()` metodo. Gli ultimi commenti mostrano l'output.  
  
     [!code-vb[VbVbalrArrays#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#31)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a>Per inizializzare una variabile di matrice irregolare usando valori letterali di matrice  
  
- Annidare i valori degli oggetti racchiusi tra parentesi graffe ( `{}` ). Sebbene sia anche possibile annidare i valori letterali di matrice che specificano matrici di lunghezze diverse, nel caso di una matrice di matrici, assicurarsi che i valori letterali di matrice annidati siano racchiusi tra parentesi ( `()` ). Le parentesi forzano la valutazione dei valori letterali di matrice annidati e le matrici risultanti vengono usate come valori iniziali della matrice di matrici. Nell'esempio di codice seguente vengono illustrati due esempi di inizializzazione di matrici di matrici.  
  
     [!code-vb[VbVbalrArrays#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#19)]  
  
- Nell'esempio seguente viene eseguita l'iterazione di una matrice di matrici. In un'applicazione console di Windows scritta in Visual Basic, incollare il codice all'interno del `Sub Main()` metodo.  Gli ultimi commenti nel codice mostrano l'output.  
  
     [!code-vb[VbVbalrArrays#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Vedere anche

- [Matrici](index.md)
- [Risoluzione dei problemi relativi alle matrici](troubleshooting-arrays.md)
