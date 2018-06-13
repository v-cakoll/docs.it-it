---
title: 'Procedura: accedere agli argomenti della riga di comando utilizzando foreach (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
ms.openlocfilehash: 2f1723efd4056539e12605bc1a4229f94bc9e055
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332507"
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a>Procedura: accedere agli argomenti della riga di comando utilizzando foreach (Guida per programmatori C#)
Un altro approccio per eseguire l'iterazione della matrice consiste nell'usare l'istruzione [foreach](../../../csharp/language-reference/keywords/foreach-in.md), come illustrato in questo esempio. L'istruzione `foreach` può essere usata per eseguire l'iterazione di una matrice, una classe di raccolte .NET Framework o qualsiasi classe o struct che implementa l'interfaccia <xref:System.Collections.IEnumerable>.  
  
> [!NOTE]
>  Quando si esegue un'applicazione in Visual Studio, è possibile specificare argomenti della riga di comando nella [Pagina Debug, Progettazione progetti](/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come stampare gli argomenti della riga di comando usando `foreach`.  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Array>  
 <xref:System.Collections>  
 [Compilazione dalla riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
 [Main() e argomenti della riga di comando](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [Procedura: Visualizzare gli argomenti della riga di comando](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [Valori restituiti da Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
