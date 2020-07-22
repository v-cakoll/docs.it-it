---
title: Come definire le proprietà astratte-guida per programmatori C#
description: Informazioni su come definire le proprietà astratte in C#. La dichiarazione di una proprietà astratta indica che una classe supporta una proprietà. Le classi derivate implementano le funzioni di accesso.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: 4db71721495857c634e8090b986704d8a592b4e2
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864397"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a>Come definire proprietà astratte (Guida per programmatori C#)
L'esempio seguente mostra come definire proprietà di tipo [abstract](../../language-reference/keywords/abstract.md). La dichiarazione di una proprietà astratta non fornisce un'implementazione delle funzioni di accesso della proprietà. Dichiara che la classe supporta le proprietà, ma l'implementazione delle funzioni di accesso viene demandata alle classi derivate. L'esempio seguente illustra come implementare le proprietà astratte ereditate da una classe di base.  
  
 L'esempio include tre file, ognuno dei quali viene compilato singolarmente e al cui assembly risultante viene fatto riferimento nella compilazione successiva:  
  
- abstractshape.cs: classe `Shape` che contiene una proprietà `Area` astratta.  
  
- shapes.cs: sottoclassi della classe `Shape`.  
  
- shapetest.cs: programma di test per la visualizzazione delle aree di alcuni oggetti derivati da `Shape`.  
  
 Per compilare l'esempio, usare il comando seguente:  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 Verrà creato il file eseguibile shapetest.exe.  
  
## <a name="example"></a>Esempio  
 Questo file dichiara la classe `Shape` che contiene la proprietà `Area` del tipo `double`.  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- I modificatori della proprietà vengono inseriti nella dichiarazione della proprietà stessa. ad esempio:  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- Quando si dichiara una proprietà astratta, come `Area` in questo esempio, è sufficiente indicare le funzioni di accesso disponibili per la proprietà, senza implementarle. In questo esempio è disponibile solo una funzione di accesso [get](../../language-reference/keywords/get.md), quindi la proprietà è di sola lettura.  
  
## <a name="example"></a>Esempio  
 Il codice seguente mostra tre sottoclassi di `Shape` e il modo in cui eseguono l'override della proprietà `Area` per fornire la propria implementazione.  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente mostra un programma di test che crea diversi oggetti derivati da `Shape` e stampa le relative aree.  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Classi e membri delle classi astratte e sealed](./abstract-and-sealed-classes-and-class-members.md)
- [Proprietà](./properties.md)
