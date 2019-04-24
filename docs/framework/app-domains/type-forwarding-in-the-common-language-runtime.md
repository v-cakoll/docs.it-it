---
title: Inoltro dei tipi in Common Language Runtime
ms.date: 03/30/2017
dev_langs:
- csharp
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e378eb36e633575d5afa886e886aed302cbdab9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310982"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a>Inoltro dei tipi in Common Language Runtime
L'inoltro dei tipi consente di spostare un tipo in un altro assembly senza dover ricompilare le applicazioni in cui viene utilizzato l'assembly originale.  
  
 Si supponga ad esempio che in un'applicazione venga utilizzata la classe `Example` in un assembly denominato `Utility.dll`. Gli sviluppatori dell'assembly `Utility.dll` possono decidere di eseguire il refactoring dell'assembly e di spostare nel corso del processo la classe `Example` in un altro assembly. Se la versione precedente dell'assembly `Utility.dll` viene sostituita con la nuova versione dell'assembly `Utility.dll` e l'assembly complementare, l'applicazione in cui viene utilizzata la classe `Example` avrà esito negativo perché non è possibile trovare la classe `Example` nella nuova versione dell'assembly `Utility.dll`.  
  
 Gli sviluppatori di `Utility.dll` possono evitare questo problema inoltrando le richieste per la classe `Example` mediante l'attributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>. Se l'attributo è stato applicato alla nuova versione dell'assembly `Utility.dll`, le richieste della classe `Example` verranno inoltrate all'assembly in cui è ora contenuta la classe e l'applicazione esistente continuerà a funzionare normalmente, senza ricompilazione.  
  
> [!NOTE]
>  In .NET Framework versione 2.0 non è possibile inoltrare i tipi da assembly scritti in Visual Basic. È tuttavia possibile utilizzare in un'applicazione scritta in Visual Basic tipi inoltrati, ovvero se nell'applicazione viene utilizzato un assembly codificato in C# o C++ e un tipo di questo assembly viene inoltrato a un altro assembly, nell'applicazione Visual Basic sarà possibile utilizzare il tipo inoltrato.  
  
## <a name="forwarding-types"></a>Inoltro di tipi  
 La procedura di inoltro dei tipi prevede quattro passaggi:  
  
1. Spostare il codice sorgente del tipo dall'assembly originale nell'assembly di destinazione.  
  
2. Nell'assembly in cui solitamente si trova il tipo usato, aggiungere un <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> per il tipo che è stato spostato. Nel codice riportato di seguito viene illustrato l'attributo per un tipo denominato `Example` che è stato spostato.  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3. Compilare l'assembly in cui è ora contenuto il tipo.  
  
4. Ricompilare l'assembly originale del tipo, con un riferimento all'assembly in cui è ora contenuto il tipo. Se ad esempio si compila un file C# dalla riga di comando, utilizzare l'opzione [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) per specificare l'assembly contenente il tipo. In C++ utilizzare la direttiva [#using](/cpp/preprocessor/hash-using-directive-cpp) nel file di origine per specificare l'assembly contenente il tipo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [Inoltro del tipo (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli)
- [Direttiva #using](/cpp/preprocessor/hash-using-directive-cpp)
