---
title: Reflection (Visual Basic)
ms.date: 07/20/2015
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
ms.openlocfilehash: d2ad8957d308aa98935c862ec1864b6682be904b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834881"
---
# <a name="reflection-visual-basic"></a>Reflection (Visual Basic)
La reflection specifica oggetti di tipo <xref:System.Type> che descrivono assembly, moduli e tipi. È possibile usare la reflection per creare in modo dinamico un'istanza di un tipo, associare il tipo a un oggetto esistente oppure ottenere il tipo da un oggetto esistente e richiamarne i metodi o accedere ai relativi campi e proprietà. Se si usano attributi nel codice, la reflection consente di accedervi. Per altre informazioni, vedere [Attributi](../../../standard/attributes/index.md).  
  
 Di seguito è riportato un esempio semplice di reflection che usa il metodo statico `GetType` ereditato da tutti i tipi dalla classe di base `Object` per ottenere il tipo di una variabile:  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 L'output è:  
  
 `System.Int32`  
  
 L'esempio seguente usa la reflection per ottenere il nome completo dell'assembly caricato.  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 L'output è:  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a>Panoramica della reflection  
 La reflection è utile nelle situazioni seguenti:  
  
-   Quando è necessario accedere agli attributi nei metadati del programma. Per altre informazioni, vedere [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md).  
  
-   Per esaminare e creare istanze di tipi in un assembly.  
  
-   Per creare nuovi tipi in fase di esecuzione. Usare le classi in <xref:System.Reflection.Emit>.  
  
-   Per eseguire l'associazione tardiva, accedere ai metodi per i tipi creati in fase di esecuzione. Vedere l'argomento relativo a [caricamento e uso dinamico dei tipi](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
## <a name="related-sections"></a>Sezioni correlate  
 Per ulteriori informazioni:  
  
-   [Reflection](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [Visualizzazione delle informazioni sul tipo](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [Reflection e tipi generici](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori Visual Basic](../../../visual-basic/programming-guide/index.md)
- [Assembly in Common Language Runtime](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md)
