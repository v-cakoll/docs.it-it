---
title: Compilazione di un progetto di interoperabilità
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cb23eb652cd769a0f3387833a9ece507479c464
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56218970"
---
# <a name="compiling-an-interop-project"></a>Compilazione di un progetto di interoperabilità

I progetti di interoperabilità COM che fanno riferimento a uno o più assembly contenenti tipi COM importati vengono compilati come qualunque altro progetto gestito. È possibile fare riferimento agli assembly di interoperabilità in un ambiente di sviluppo quale Visual Studio oppure da un compilatore da riga di comando. In entrambi i casi, perché la compilazione sia corretta, l'assembly di interoperabilità deve trovarsi nella stessa directory degli altri file di progetto.

 Esistono due modi per fare riferimento agli assembly di interoperabilità:

-   Tipi di interoperabilità incorporati: a partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] e Visual Studio 2010, è possibile indicare al compilatore di incorporare nell'eseguibile informazioni sul tipo ottenute da un assembly di interoperabilità. Questa è la tecnica consigliata.

-   Distribuzione di assembly di interoperabilità: è possibile creare un riferimento standard a un assembly di interoperabilità. In questo caso, l'assembly di interoperabilità deve essere distribuito con l'applicazione.

 Le differenze tra queste due tecniche sono discusse più dettagliatamente in [Uso dei tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).

 L'incorporamento dei tipi di interoperabilità con Visual Studio è illustrato in [Procedura dettagliata: Incorporamento delle informazioni sui tipi da assembly di Microsoft Office (C# e Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee317478(v=vs.100)), [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (C#)](/docs/csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) e [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (Visual Basic)](/docs/visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md).

 Per fare riferimento a un assembly di interoperabilità con un compilatore da riga di comando e incorporare le informazioni sul tipo negli eseguibili, usare l'opzione del compilatore [/link (opzioni del compilatore C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) e specificare il nome dell'assembly.

> [!NOTE]
> Le applicazioni Visual C++ non possono incorporare informazioni sul tipo, ma possono interagire con applicazioni o componenti aggiuntivi in grado di farlo.

 Per compilare un'applicazione che includa un assembly di interoperabilità primario quando viene distribuita, usare l'opzione del compilatore **/reference** e specificare il nome dell'assembly.

## <a name="see-also"></a>Vedere anche

- [Esposizione di componenti COM a .NET Framework](exposing-com-components.md)
- [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../standard/language-independence-and-language-independent-components.md)
- [Uso dei tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Procedura dettagliata: Incorporamento delle informazioni sui tipi da assembly di Microsoft Office in Visual Studio (C#)](../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-type-information-from-microsoft-office-assemblies.md) 
- [Procedura dettagliata: Incorporamento delle informazioni sui tipi da assembly di Microsoft Office in Visual Studio (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-vs.md)
- [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (C#)](/docs/csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)
- [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (Visual Basic)](/docs/visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [Importazione di una libreria dei tipi come assembly](importing-a-type-library-as-an-assembly.md)