---
title: Creazione di assembly
ms.date: 08/19/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2dda45cca182d75bc77916cdf862ada9faead9ec
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70973306"
---
# <a name="create-assemblies"></a>Creazione di assembly

È possibile creare assembly con uno o più file usando un ambiente IDE, ad esempio Visual Studio, oppure con i compilatori e gli strumenti forniti da Windows SDK. L'assembly più semplice è costituito da un unico file con un nome semplice, caricato in un unico dominio dell'applicazione. Altri assembly all'esterno della directory dell'applicazione non possono fare riferimento a questo assembly, che non può neanche essere sottoposto al controllo della versione. Per disinstallare l'applicazione costituita dall'assembly, è sufficiente eliminare la directory in cui si trova. Per molti sviluppatori un assembly con queste funzionalità è tutto ciò che serve per distribuire un'applicazione.

È possibile creare un assembly su più file da diversi moduli di codice e file di risorse. È anche possibile creare un assembly che può essere condiviso da più applicazioni. Un assembly condiviso deve avere un nome sicuro e può essere distribuito nella Global Assembly Cache.

Quando si raggruppano moduli di codice e risorse negli assembly, sono disponibili diverse opzioni in base ai fattori seguenti:

- Controllo delle versioni

     Raggruppare i moduli che devono avere le stesse informazioni sulla versione.

- Distribuzione

     Raggruppare i moduli di codice e le risorse che supportano il modello di distribuzione usato.

- Riuso

     Raggruppare i moduli se possono essere usati insieme in modo logico per uno scopo. Ad esempio, è possibile inserire nello stesso assembly un assembly costituito da tipi e classi usati raramente per la manutenzione di programmi. In più, i tipi che si intende condividere più applicazioni devono essere raggruppati in un assembly, che deve essere firmato con un nome sicuro.

- Security

     Raggruppare moduli contenenti tipi che richiedono le stesse autorizzazioni di sicurezza.

- Ambito

     Raggruppare moduli contenenti tipi la cui visibilità deve essere limitata allo stesso assembly.

Quando si rendono disponibili assembly Common Language Runtime alle applicazioni COM non gestite, è necessario tenere presenti alcune considerazioni speciali. Per ulteriori informazioni sull'utilizzo di codice non gestito, vedere [esporre componenti .NET Framework a com](../../framework/interop/exposing-dotnet-components-to-com.md).

## <a name="see-also"></a>Vedere anche

- [Programma con assembly](program.md)
- [Controllo delle versioni degli assembly](versioning.md)
- [Procedura: Compilare un assembly a file singolo](../../framework/app-domains/build-single-file-assembly.md)
- [Procedura: Compilare un assembly su più file](../../framework/app-domains/build-multifile-assembly.md)
- [Come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [Assembly su più file](../../framework/app-domains/multifile-assemblies.md)
