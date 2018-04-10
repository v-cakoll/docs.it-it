---
title: this (Riferimenti per C#)
description: Parola chiave this (Riferimenti per C#)
keywords: this (C#), parola chiave this (C#), parola chiave this (Riferimenti per C#), parola chiave this (Riferimenti per il linguaggio C#)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f159967707061481a34e72a97ec8cc8316d982ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="this-c-reference"></a>this (Riferimenti per C#)
La parola chiave `this` fa riferimento all'istanza corrente della classe e viene anche usata come modificatore del primo parametro di un metodo di estensione.  
  
> [!NOTE]
>  Questo articolo illustra l'uso di `this` con istanze della classe. Per altre informazioni sull'uso nei metodi di estensione, vedere [Metodi di estensione](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
 Di seguito sono riportati gli usi comuni di `this`:  
  
-   Per qualificare i membri nascosti da nomi simili, ad esempio:  
  
 [!code-csharp[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   Per passare un oggetto come parametro ad altri metodi, ad esempio:  
  
    ```  
    CalcTax(this);  
    ```  
  
-   Per dichiarare gli indicizzatori, ad esempio:  
  
 [!code-csharp[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 Le funzioni del membro statico, perché esistono a livello di classe e non come parte di un oggetto, non dispongono di un puntatore `this`. È un errore fare riferimento a `this` in un metodo statico.  
  
## <a name="example"></a>Esempio  
 In questo esempio, `this` viene usato per qualificare i membri della classe `Employee`, `name` e `alias`, che sono nascosti da nomi simili. Viene anche usato per passare un oggetto al metodo `CalcTax`, che appartiene a un'altra classe.  
  
 [!code-csharp[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [base](../../../csharp/language-reference/keywords/base.md)  
 [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md)
