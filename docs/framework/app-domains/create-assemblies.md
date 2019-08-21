---
title: Creazione degli assembly
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 314a94be140b392964951299fba2fed4ac7e6e68
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566785"
---
# <a name="creating-assemblies"></a>Creazione degli assembly

È possibile creare assembly con uno o più file usando un ambiente IDE, ad esempio Visual Studio, oppure con i compilatori e gli strumenti forniti da Windows SDK. L'assembly più semplice è costituito da un unico file con un nome semplice, caricato in un unico dominio dell'applicazione. Altri assembly all'esterno della directory dell'applicazione non possono fare riferimento a questo assembly, che non può neanche essere sottoposto al controllo della versione. Per disinstallare l'applicazione costituita dall'assembly, è sufficiente eliminare la directory in cui si trova. Per molti sviluppatori un assembly con queste funzionalità è tutto ciò che serve per distribuire un'applicazione.

È possibile creare un assembly su più file da diversi moduli di codice e file di risorse. È anche possibile creare un assembly che può essere condiviso da più applicazioni. Un assembly condiviso deve avere un nome sicuro e può essere distribuito nella Global Assembly Cache.

Quando si raggruppano moduli di codice e risorse negli assembly, sono disponibili diverse opzioni in base ai fattori seguenti:

- Controllo delle versioni

     Raggruppare i moduli che devono avere le stesse informazioni sulla versione.

- Distribuzione

     Raggruppare i moduli di codice e le risorse che supportano il modello di distribuzione usato.

- Riuso

     Raggruppare i moduli se possono essere usati insieme in modo logico per uno scopo. Ad esempio, è possibile inserire nello stesso assembly un assembly costituito da tipi e classi usati raramente per la manutenzione di programmi. In più, i tipi che si intende condividere più applicazioni devono essere raggruppati in un assembly, che deve essere firmato con un nome sicuro.

- Sicurezza

     Raggruppare moduli contenenti tipi che richiedono le stesse autorizzazioni di sicurezza.

- Ambito

     Raggruppare moduli contenenti tipi la cui visibilità deve essere limitata allo stesso assembly.

Sono necessarie considerazioni speciali quando si rendono disponibili assembly Common Language Runtime ad applicazioni COM non gestite. Per altre informazioni sull'uso di codice non gestito, vedere [Esposizione di componenti .NET Framework a COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).

## <a name="see-also"></a>Vedere anche

- [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [Controllo delle versioni degli assembly](../../../docs/framework/app-domains/assembly-versioning.md)
- [Procedura: Compilare un assembly su singolo file](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)
- [Procedura: Compilare un assembly con più file](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Assembly su più file](../../../docs/framework/app-domains/multifile-assemblies.md)
