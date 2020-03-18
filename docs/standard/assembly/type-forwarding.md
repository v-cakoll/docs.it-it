---
title: Inoltro dei tipi in Common Language Runtime
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: 215636a9617a2723d8ab69640c1d3e69491a7d87
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160365"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a>Inoltro dei tipi in Common Language Runtime
L'inoltro dei tipi consente di spostare un tipo in un altro assembly senza dover ricompilare le applicazioni in cui viene utilizzato l'assembly originale.  
  
 Si supponga, ad esempio, che un'applicazione utilizzi la `Example` classe in un assembly denominato *Utility.dll*. Gli sviluppatori di *Utility.dll* potrebbero decidere di eseguire il refactoring dell'assembly e, nel processo, potrebbero spostare la `Example` classe in un altro assembly. Se la versione precedente di *Utility.dll* viene sostituita dalla nuova versione di *Utility.dll* e dal relativo assembly complementare, l'applicazione che utilizza la `Example` classe ha esito negativo perché non è in grado di individuare la `Example` classe nella nuova versione di *Utility.dll*.  
  
 Gli sviluppatori di *Utility.dll* possono evitare `Example` questo inoltrando le richieste per la classe, utilizzando l'attributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> . Se l'attributo è stato applicato alla nuova versione `Example` di *Utility.dll*, le richieste per la classe vengono inoltrate all'assembly che ora contiene la classe . e l'applicazione esistente continuerà a funzionare normalmente, senza ricompilazione.  
  
> [!NOTE]
> In .NET Framework versione 2.0 non è possibile inoltrare i tipi da assembly scritti in Visual Basic. È tuttavia possibile utilizzare in un'applicazione scritta in Visual Basic tipi inoltrati, ovvero se nell'applicazione viene utilizzato un assembly codificato in C# o C++ e un tipo di questo assembly viene inoltrato a un altro assembly, nell'applicazione Visual Basic sarà possibile utilizzare il tipo inoltrato.  
  
## <a name="forward-types"></a>Tipi di inoltro  
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

4. Ricompilare l'assembly originale del tipo, con un riferimento all'assembly in cui è ora contenuto il tipo. Se, ad esempio, si sta compilando un file di C, utilizzare l'opzione [-reference (opzioni del compilatore C)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) per specificare l'assembly che contiene il tipo. In C++ utilizzare la direttiva [#using](/cpp/preprocessor/hash-using-directive-cpp) nel file di origine per specificare l'assembly contenente il tipo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [Inoltro dei tipi (C](/cpp/windows/type-forwarding-cpp-cli)
- [#using direttiva](/cpp/preprocessor/hash-using-directive-cpp)
