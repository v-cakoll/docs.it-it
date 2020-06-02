---
title: Espressioni lambda in PLINQ e TPL
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
ms.openlocfilehash: 3d985a003fe613699c89e38583f84be9e21b383d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290668"
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a>Espressioni lambda in PLINQ e TPL

Task Parallel Library (TPL) contiene numerosi metodi che accettano una delle famiglie di delegati <xref:System.Func%601?displayProperty=nameWithType> o <xref:System.Action?displayProperty=nameWithType> come parametri di input. Questi delegati vengono usati per passare la logica di programma personalizzata al ciclo, all'attività o alla query parallela. Gli esempi di codice per TPL e PLINQ usano espressioni lambda per creare istanze dei delegati come blocchi di codice inline. Questo argomento offre una breve introduzione a Func e Action e illustra come usare le espressioni lambda in TPL e PLINQ.

> [!NOTE]
> Per ulteriori informazioni sui delegati in generale [, vedere delegati](../../csharp/programming-guide/delegates/index.md) [e delegati](../../visual-basic/programming-guide/language-features/delegates/index.md). Per altre informazioni sulle espressioni lambda in C# e Visual Basic, vedere [Espressioni lambda (Guida per programmatori C#)](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) e [Espressioni lambda (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="func-delegate"></a>Delegato Func

Un delegato `Func` incapsula un metodo che restituisce un valore. In una `Func` firma, l'ultimo parametro di tipo, o più a destra, specifica sempre il tipo restituito. Una causa comune degli errori del compilatore è il tentativo di passare due parametri di input a un tipo <xref:System.Func%602?displayProperty=nameWithType>, che accetta un solo parametro di input. .NET definisce 17 versioni di `Func` : <xref:System.Func%601?displayProperty=nameWithType> , <xref:System.Func%602?displayProperty=nameWithType> , <xref:System.Func%603?displayProperty=nameWithType> e così via fino a <xref:System.Func%6017?displayProperty=nameWithType> .

## <a name="action-delegate"></a>Delegato Action

Un <xref:System.Action?displayProperty=nameWithType> delegato incapsula un metodo (Sub in Visual Basic) che non restituisce un valore. In una `Action` firma di tipo, i parametri di tipo rappresentano solo parametri di input. Analogamente a `Func` , .NET definisce 17 versioni di `Action` , da una versione priva di parametri di tipo fino a una versione con 16 parametri di tipo.

## <a name="example"></a>Esempio

L'esempio seguente per il metodo <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> mostra come esprimere entrambi i delegati Func e Action usando espressioni lambda.

[!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
[!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]

## <a name="see-also"></a>Vedere anche

- [Programmazione parallela](index.md)
