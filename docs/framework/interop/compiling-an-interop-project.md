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
ms.openlocfilehash: 32102910ae674a97e941e1346a1898585f503527
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123676"
---
# <a name="compiling-an-interop-project"></a>Compilazione di un progetto di interoperabilità

I progetti di interoperabilità COM che fanno riferimento a uno o più assembly contenenti tipi COM importati vengono compilati come qualunque altro progetto gestito. È possibile fare riferimento agli assembly di interoperabilità in un ambiente di sviluppo quale Visual Studio oppure da un compilatore da riga di comando. In entrambi i casi, perché la compilazione sia corretta, l'assembly di interoperabilità deve trovarsi nella stessa directory degli altri file di progetto.

 Esistono due modi per fare riferimento agli assembly di interoperabilità:

- Tipi di interoperabilità incorporati: a partire da .NET Framework 4 e Visual Studio 2010, è possibile indicare al compilatore di incorporare le informazioni sui tipi da un assembly di interoperabilità nell'eseguibile. Questa è la tecnica consigliata.

- Distribuzione di assembly di interoperabilità: è possibile creare un riferimento standard a un assembly di interoperabilità. In questo caso, l'assembly di interoperabilità deve essere distribuito con l'applicazione.

 Le differenze tra queste due tecniche sono discusse più dettagliatamente in [Uso dei tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).

 L'incorporamento dei tipi di interoperabilità con Visual Studio è illustrato in [procedura dettagliata: incorporamento di tipi da assembly gestiti in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).

 Per fare riferimento a un assembly di interoperabilità con un compilatore da riga di comando e incorporare le informazioni sui tipi nei file eseguibili, usare l'opzione [-link (opzioni del compilatore C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) o l'opzione [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) del compilatore e specificare il nome dell'assembly di interoperabilità.

> [!NOTE]
> Le applicazioni Visual C++ non possono incorporare informazioni sul tipo, ma possono interagire con applicazioni o componenti aggiuntivi in grado di farlo.

 Per compilare un'applicazione che includa un assembly di interoperabilità primario quando viene distribuita, usare l'opzione del compilatore **/reference** e specificare il nome dell'assembly.

## <a name="see-also"></a>Vedere anche

- [Esposizione di componenti COM a .NET Framework](exposing-com-components.md)
- [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../standard/language-independence-and-language-independent-components.md)
- [Uso dei tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio](../../standard/assembly/embed-types-visual-studio.md)
- [Importazione di una libreria dei tipi come assembly](importing-a-type-library-as-an-assembly.md)
