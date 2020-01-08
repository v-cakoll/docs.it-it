---
title: Contenuto degli assembly
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework]
- assemblies [.NET Core]
- single-file assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
ms.openlocfilehash: bee9d5422ec3101b2486f233ae0816ae3643f4e7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345580"
---
# <a name="assembly-contents"></a>Contenuto degli assembly

Per grandi linee, un assembly statico è costituito da quattro elementi:

- Il [manifesto dell'assembly](manifest.md) che contiene i metadati dell'assembly.

- I metadati dei tipi.  

- Il codice Microsoft Intermediate Language (MSIL) che implementa i tipi. Viene generato dal compilatore da uno o più file di codice sorgente.

- Set di [risorse](../../framework/resources/index.md).  

Il manifesto dell'assembly è il solo elemento obbligatorio, ma il corretto funzionamento dell'assembly dipende anche dalla presenza di tipi o risorse.

Nella figura seguente vengono illustrati questi elementi raggruppati in un singolo file fisico:

![Assembly A file singolo denominato myAssembly. dll](./media/contents/single-file-assembly.gif)

Quando si progetta il codice sorgente, si prendono decisioni esplicite su come partizionare le funzionalità dell'applicazione in uno o più file. Quando si progetta il codice .NET, è possibile prendere decisioni simili su come partizionare le funzionalità in uno o più assembly.

## <a name="see-also"></a>Vedere anche

- [Assembly in .NET](index.md)
- [Manifesto dell'assembly](manifest.md)
- [Considerazioni sulla sicurezza degli assembly](security-considerations.md)
