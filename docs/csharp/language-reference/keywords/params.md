---
title: params (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 692c2f61ae99f1c1c8e04a5a1bcad08814d286fe
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752093"
---
# <a name="params-c-reference"></a>params (Riferimenti per C#)
Usando la parola chiave `params`, è possibile specificare un [parametro di metodo](../../../csharp/language-reference/keywords/method-parameters.md) che usa un numero variabile di argomenti.  
  
 È possibile inviare un elenco di argomenti separato da virgole del tipo specificato nella dichiarazione di parametri o una matrice di argomenti del tipo specificato. È anche possibile non inviare alcun argomento. Se non vengono inviati argomenti, la lunghezza dell'elenco `params` è zero.  
  
 In una dichiarazione di metodo non è possibile aggiungere altri parametri dopo la parola chiave `params` ed è consentito l'uso di una sola parola chiave `params`.  
 
 Il tipo dichiarato del parametro `params` deve essere una matrice unidimensionale, come illustrato nell'esempio seguente. In caso contrario, si verifica l'errore del compilatore [CS0225](../../../csharp/misc/cs0225.md).
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrati i vari modi in cui è possibile inviare argomenti al parametro `params`.  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Parametri dei metodi](../../../csharp/language-reference/keywords/method-parameters.md)
