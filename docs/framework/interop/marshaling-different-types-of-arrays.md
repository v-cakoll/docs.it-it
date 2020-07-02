---
title: Marshalling di diversi tipi di matrici
description: Eseguire il marshalling di tipi di matrice diversi, ad esempio interi per valore o riferimento, interi bidimensionali per valore, stringhe per valore e strutture con Integer o stringhe.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
ms.openlocfilehash: f1473c7917189f0b36c96b2adcf20005c5fd6b48
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621496"
---
# <a name="marshaling-different-types-of-arrays"></a>Marshalling di diversi tipi di matrici
Una matrice è un tipo di riferimento nel codice gestito che contiene uno o più elementi dello stesso tipo. Anche se le matrici sono tipi di riferimento, vengono passate come parametri in alle funzioni non gestite. Questo comportamento non è coerente con il modo in cui le matrici gestite vengono passate agli oggetti gestiti, ovvero come parametri in/out. Per altri dettagli, vedere [Copia e blocco](copying-and-pinning.md).  
  
 La tabella seguente elenca le opzioni di marshalling delle matrici e ne descrive l'utilizzo.  
  
|Array|Descrizione|  
|-----------|-----------------|  
|Di Integer in base al valore.|Passa una matrice di Integer come un parametro in.|  
|Di Integer in base al riferimento.|Passa una matrice di Integer come un parametro in/out.|  
|Di Integer in base al valore (bidimensionale).|Passa una matrice di Integer come un parametro in.|  
|Di stringhe in base al valore.|Passa una matrice di stringhe come un parametro in.|  
|Di strutture con Integer.|Passa una matrice di strutture che contengono Integer come un parametro in.|  
|Di strutture con stringhe.|Passa una matrice di strutture che contengono solo stringhe come parametro In/Out. È possibile modificare i membri della matrice.|  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra come passare i tipi di matrice seguenti:  
  
- Matrice di Integer in base al valore.  
  
- Matrice di Integer in base al riferimento, che è possibile ridimensionare.  
  
- Matrice multidimensionale di Integer in base al valore.  
  
- Matrice di stringhe in base al valore.  
  
- Matrice di strutture con Integer.  
  
- Matrice di strutture con stringhe.  
  
 A meno che non venga eseguito il marshalling esplicito di una matrice in base al riferimento, il comportamento predefinito esegue il marshalling della matrice come un parametro in. È possibile modificare questo comportamento applicando in modo esplicito gli attributi <xref:System.Runtime.InteropServices.InAttribute> e <xref:System.Runtime.InteropServices.OutAttribute> .  
  
 Nell'esempio di matrici vengono usate le seguenti funzioni non gestite, illustrate con le dichiarazioni di funzione originali:  
  
- **TestArrayOfInts** esportata da PinvokeLib.dll.  
  
    ```cpp
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
- **TestRefArrayOfInts** esportata da PinvokeLib.dll.  
  
    ```cpp
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
- **TestMatrixOfInts** esportata da PinvokeLib.dll.  
  
    ```cpp
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
- **TestArrayOfStrings** esportata da PinvokeLib.dll.  
  
    ```cpp
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
- **TestArrayOfStructs** esportata da PinvokeLib.dll.  
  
    ```cpp
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
- **TestArrayOfStructs2** esportata da PinvokeLib.dll.  
  
    ```cpp
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 [PinvokeLib](marshaling-data-with-platform-invoke.md#pinvokelibdll) è una libreria non gestita personalizzata contenente implementazioni per le funzioni elencate in precedenza e due variabili di struttura, ovvero **MYPOINT** e **MYPERSON**. Le strutture contengono gli elementi seguenti:  
  
```cpp
typedef struct _MYPOINT  
{  
   int x;
   int y;
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;
   char* last;
} MYPERSON;  
```  
  
 In questo esempio, le strutture `MyPoint` e `MyPerson` contengono tipi incorporati. L'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> è impostato in modo da garantire che i membri vengano inseriti in memoria in sequenza, nell'ordine in cui appaiono.  
  
 La classe `NativeMethods` contiene un set di metodi chiamati dalla classe `App` . Per informazioni specifiche sul passaggio di matrici, vedere i commenti nell'esempio seguente. Una matrice, che è un tipo di riferimento, viene passata come un parametro in per impostazione predefinita. Per permettere al chiamante di ricevere i risultati, **InAttribute** e **OutAttribute** devono essere applicati in modo esplicito all'argomento contenente la matrice.  
  
### <a name="declaring-prototypes"></a>Dichiarazione dei prototipi  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a>Chiamata delle funzioni  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati PInvoke](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [Creazione di prototipi nel codice gestito](creating-prototypes-in-managed-code.md)
