---
title: 'Procedura: definire proprietà astratte (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: aa9006b6864b9b6b129eed323b0d6d7b29064189
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172061"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a>Procedura: definire proprietà astratte (Guida per programmatori C#)
L'esempio seguente mostra come definire proprietà di tipo [abstract](../../../csharp/language-reference/keywords/abstract.md). La dichiarazione di una proprietà astratta non fornisce un'implementazione delle funzioni di accesso della proprietà. Dichiara che la classe supporta le proprietà, ma l'implementazione delle funzioni di accesso viene demandata alle classi derivate. L'esempio seguente illustra come implementare le proprietà astratte ereditate da una classe di base.  
  
 L'esempio include tre file, ognuno dei quali viene compilato singolarmente e al cui assembly risultante viene fatto riferimento nella compilazione successiva:  
  
-   abstractshape.cs: classe `Shape` che contiene una proprietà `Area` astratta.  
  
-   shapes.cs: sottoclassi della classe `Shape`.  
  
-   shapetest.cs: programma di test per la visualizzazione delle aree di alcuni oggetti derivati da `Shape`.  
  
 Per compilare l'esempio, usare il comando seguente:  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 Verrà creato il file eseguibile shapetest.exe.  
  
## <a name="example"></a>Esempio  
 Questo file dichiara la classe `Shape` che contiene la proprietà `Area` del tipo `double`.  
  
 [!code-csharp[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_1.cs)]  
  
-   I modificatori della proprietà vengono inseriti nella dichiarazione della proprietà stessa. Ad esempio:  
  
    ```csharp  
    public abstract double Area  
    ```  
  
-   Quando si dichiara una proprietà astratta, come `Area` in questo esempio, è sufficiente indicare le funzioni di accesso disponibili per la proprietà, senza implementarle. In questo esempio è disponibile solo una funzione di accesso [get](../../../csharp/language-reference/keywords/get.md), quindi la proprietà è di sola lettura.  
  
## <a name="example"></a>Esempio  
 Il codice seguente mostra tre sottoclassi di `Shape` e il modo in cui eseguono l'override della proprietà `Area` per fornire la propria implementazione.  
  
 [!code-csharp[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_2.cs)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente mostra un programma di test che crea diversi oggetti derivati da `Shape` e stampa le relative aree.  
  
 [!code-csharp[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_3.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Classi e membri delle classi astratte e sealed](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
 [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Procedura: Creare e usare assembly dalla riga di comando](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)
