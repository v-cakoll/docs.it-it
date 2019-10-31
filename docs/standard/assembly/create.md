---
title: Creare assembly
ms.date: 08/19/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
ms.openlocfilehash: 8a00784e6aa2d663c738339367b4076e79ed9c95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122491"
---
# <a name="create-assemblies"></a>Creare assembly

È possibile creare assembly con uno o più file usando un ambiente IDE, ad esempio Visual Studio, oppure con i compilatori e gli strumenti forniti da Windows SDK. L'assembly più semplice è costituito da un unico file con un nome semplice, caricato in un unico dominio dell'applicazione. Altri assembly all'esterno della directory dell'applicazione non possono fare riferimento a questo assembly, che non può neanche essere sottoposto al controllo della versione. Per disinstallare l'applicazione costituita dall'assembly, è sufficiente eliminare la directory in cui si trova. Per molti sviluppatori un assembly con queste funzionalità è tutto ciò che serve per distribuire un'applicazione.

È possibile creare un assembly su più file da diversi moduli di codice e file di risorse. È anche possibile creare un assembly che può essere condiviso da più applicazioni. Un assembly condiviso deve avere un nome sicuro e può essere distribuito nella Global Assembly Cache.

Quando si raggruppano moduli di codice e risorse negli assembly, sono disponibili diverse opzioni in base ai fattori seguenti:

- Versionamento

     Raggruppare i moduli che devono avere le stesse informazioni sulla versione.

- Distribuzione

     Raggruppare i moduli di codice e le risorse che supportano il modello di distribuzione usato.

- Riuso

     Raggruppare i moduli se possono essere usati insieme in modo logico per uno scopo. Ad esempio, è possibile inserire nello stesso assembly un assembly costituito da tipi e classi usati raramente per la manutenzione di programmi. In più, i tipi che si intende condividere più applicazioni devono essere raggruppati in un assembly, che deve essere firmato con un nome sicuro.

- Sicurezza

     Raggruppare moduli contenenti tipi che richiedono le stesse autorizzazioni di sicurezza.

- Ambito

     Raggruppare moduli contenenti tipi la cui visibilità deve essere limitata allo stesso assembly.

Quando si rendono disponibili assembly Common Language Runtime alle applicazioni COM non gestite, è necessario tenere presenti alcune considerazioni speciali. Per ulteriori informazioni sull'utilizzo di codice non gestito, vedere [esporre componenti .NET Framework a com](../../framework/interop/exposing-dotnet-components-to-com.md).

## <a name="see-also"></a>Vedere anche

- [Programma con assembly](program.md)
- [Controllo delle versioni degli assembly](versioning.md)
- [Procedura: compilare un assembly a file singolo](../../framework/app-domains/build-single-file-assembly.md)
- [Procedura: compilare un assembly su più file](../../framework/app-domains/build-multifile-assembly.md)
- [Come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [Assembly su più file](../../framework/app-domains/multifile-assemblies.md)
