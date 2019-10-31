---
title: Contenuto degli assembly
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- assemblies [.NET Core]
- single-file assemblies
- multifile assemblies [.NET Framework]
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
ms.openlocfilehash: 9ca12ee4bd993db3dd200a3b340c220ce5188796
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122540"
---
# <a name="assembly-contents"></a>Contenuto degli assembly
Per grandi linee, un assembly statico è costituito da quattro elementi:

- Il [manifesto dell'assembly](manifest.md) che contiene i metadati dell'assembly.

- I metadati dei tipi.  

- Il codice Microsoft Intermediate Language (MSIL) che implementa i tipi. Viene generato dal compilatore da uno o più file di codice sorgente.

- Un insieme di risorse.  

Il manifesto dell'assembly è il solo elemento obbligatorio, ma il corretto funzionamento dell'assembly dipende anche dalla presenza di tipi o risorse.

Nella figura seguente vengono illustrati questi elementi raggruppati in un singolo file fisico.

![Diagramma che illustra un assembly a file singolo denominato MyAssembly.dll.](./media/contents/single-file-assembly.gif)

Nella figura riportata di seguito tutti e tre i file appartengono a un assembly, come descritto nel manifesto dell'assembly contenuto in MyAssembly.dll. Tali file vengono gestiti dal file system come tre file distinti. Si noti che il file Util.netmodule è stato compilato come modulo perché in esso non sono contenute informazioni sull'assembly. Quando è stato creato l'assembly, il relativo manifesto è stato aggiunto a MyAssembly.dll, indicandone la relazione con Util.netmodule e Graphic.bmp.

Oggi nella progettazione del codice sorgente si prendono decisioni esplicite su come partizionare le funzionalità della propria applicazione in uno o più file. Nel progettare codice .NET Framework, si prenderanno decisioni simili riguardo a come partizionare le funzionalità in uno o più assembly.

## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](index.md)
- [Manifesto dell'assembly](manifest.md)
- [Considerazioni sulla sicurezza degli assembly](security-considerations.md)
