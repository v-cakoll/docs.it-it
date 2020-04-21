---
title: params (parola chiave) per le matrici di parametri - Riferimento in C
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 77d7fd19ff57f80f401191027e2fae95026e1966
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738833"
---
# <a name="params-c-reference"></a>params (Riferimenti per C#)

Usando la parola chiave `params`, è possibile specificare un [parametro di metodo](method-parameters.md) che usa un numero variabile di argomenti. Il tipo di parametro deve essere una matrice unidimensionale.

In una dichiarazione di metodo non è possibile aggiungere altri parametri dopo la parola chiave `params` ed è consentito l'uso di una sola parola chiave `params`.

Se il tipo `params` dichiarato del parametro non è una matrice unidimensionale, si verifica l'errore del compilatore [CS0225.](../../misc/cs0225.md)

Quando si chiama un `params` metodo con un parametro, è possibile passare:When you call a method with a parameter, you can pass in:

- Elenco delimitato da virgole di argomenti del tipo degli elementi della matrice.
- Matrice di argomenti del tipo specificato.
- Nessun argomento. Se non vengono inviati argomenti, la lunghezza dell'elenco `params` è zero.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono illustrati i vari modi in cui è possibile inviare argomenti al parametro `params`.

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida alla programmazione in C](../../programming-guide/index.md)
- [Parole chiave di C](index.md)
- [Parametri di metodo](method-parameters.md)
