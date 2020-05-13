---
title: Inoltro dei tipi in Common Language Runtime
description: L'invio di tipi consente di spostare un tipo in un altro assembly .NET senza dover ricompilare le applicazioni che utilizzano l'assembly originale.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: f0be61bd4ce88569e22a350a9ea9490d67e74ff3
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378588"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a>Inoltro dei tipi in Common Language Runtime
L'inoltro dei tipi consente di spostare un tipo in un altro assembly senza dover ricompilare le applicazioni in cui viene utilizzato l'assembly originale.  
  
 Si supponga, ad esempio, che in un'applicazione venga utilizzata la `Example` classe in un assembly denominato *Utility. dll*. Gli sviluppatori di *Utility. dll* potrebbero decidere di effettuare il refactoring dell'assembly e nel processo potrebbero spostare la `Example` classe in un altro assembly. Se la versione precedente di *Utility. dll* viene sostituita dalla nuova versione di *Utility. dll* e dall'assembly complementare, l'applicazione che usa la `Example` classe ha esito negativo perché non è in grado di individuare la `Example` classe nella nuova versione di *Utility. dll*.  
  
 Gli sviluppatori di *Utility. dll* possono evitare questo problema tramite l'invio di richieste per la `Example` classe, usando l' <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attributo. Se l'attributo è stato applicato alla nuova versione di *Utility. dll*, le richieste per la `Example` classe vengono inviate all'assembly che ora contiene la classe. e l'applicazione esistente continuerà a funzionare normalmente, senza ricompilazione.  
  
> [!NOTE]
> In .NET Framework versione 2.0 non è possibile inoltrare i tipi da assembly scritti in Visual Basic. È tuttavia possibile utilizzare in un'applicazione scritta in Visual Basic tipi inoltrati, ovvero se nell'applicazione viene utilizzato un assembly codificato in C# o C++ e un tipo di questo assembly viene inoltrato a un altro assembly, nell'applicazione Visual Basic sarà possibile utilizzare il tipo inoltrato.  
  
## <a name="forward-types"></a>Tipi di inoltri  
 La procedura di inoltro dei tipi prevede quattro passaggi:  
  
1. Spostare il codice sorgente del tipo dall'assembly originale nell'assembly di destinazione.  

2. Nell'assembly in cui solitamente si trova il tipo usato, aggiungere un <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> per il tipo che è stato spostato. Nel codice riportato di seguito viene illustrato l'attributo per un tipo denominato `Example` che è stato spostato.  

   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```

   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  

3. Compilare l'assembly in cui è ora contenuto il tipo.  

4. Ricompilare l'assembly originale del tipo, con un riferimento all'assembly in cui è ora contenuto il tipo. Se, ad esempio, si compila un file C# dalla riga di comando, usare l'opzione [-Reference (opzioni del compilatore c#)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) per specificare l'assembly contenente il tipo. In C++ utilizzare la direttiva [#using](/cpp/preprocessor/hash-using-directive-cpp) nel file di origine per specificare l'assembly contenente il tipo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [Inoltri di tipi (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli)
- [#using (direttiva)](/cpp/preprocessor/hash-using-directive-cpp)
