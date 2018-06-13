---
title: 'Procedura: visualizzare gli argomenti della riga di comando (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 7b9e488e84c78c8fdbf64431f42ea5797fdca916
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334136"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>Procedura: visualizzare gli argomenti della riga di comando (Guida per programmatori C#)
Gli argomenti specificati per un file eseguibile dalla riga di comando sono accessibili tramite un parametro facoltativo per `Main`. Gli argomenti vengono specificati sotto forma di una matrice di stringhe. Ogni elemento della matrice contiene un solo argomento. Gli spazi vuoti tra gli argomenti vengono rimossi. Si considerino ad esempio le chiamate seguenti della riga di comando di un file eseguibile fittizio:  
  
|Input riga di comando|Matrice di stringhe passate a Main|  
|----------------------------|-------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
>  Quando si esegue un'applicazione in Visual Studio, è possibile specificare argomenti della riga di comando nella [Pagina Debug, Progettazione progetti](/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono visualizzati gli argomenti della riga di comando passati a un'applicazione della riga di comando. L'output visualizzato è per la prima voce nella tabella precedente.  
  
 [!code-csharp[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Compilazione dalla riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [Main() e argomenti della riga di comando](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [Procedura: Accedere agli argomenti della riga di comando usando foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
 [Valori restituiti da Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
