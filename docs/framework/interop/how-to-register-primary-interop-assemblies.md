---
title: 'Procedura: registrare assembly di interoperabilità primari'
ms.date: 03/30/2017
helpviewer_keywords:
- registering primary interop assemblies
- primary interop assemblies, registering
ms.assetid: 4b2fcf8a-429d-43ce-8334-e026040be8bb
ms.openlocfilehash: c799e4ead2932f1c376a57488df30390ad48b90f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107685"
---
# <a name="how-to-register-primary-interop-assemblies"></a>Procedura: registrare assembly di interoperabilità primari

È possibile effettuare il marshalling delle classi solo tramite l'interoperabilità COM e solo come interfacce. In alcuni casi l'interfaccia usata per il marshalling della classe è nota come interfaccia di classe. Per informazioni sull'override dell'interfaccia di classe con un'altra interfaccia, vedere [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md).

 Anche se gli sviluppatori che vogliono usare i tipi COM di un'applicazione .NET Framework possono generare un assembly di interoperabilità, facendolo creano un problema. Ogni volta che uno sviluppatore importa e firma una libreria di tipi COM, crea un set di tipi univoci non compatibili con quelli importati e firmati da un altro sviluppatore. Per risolvere questo problema di incompatibilità dei tipi, ogni sviluppatore deve ottenere l'assembly di interoperabilità primario fornito e firmato dal fornitore.

 Se si prevede di esporre tipi COM di terze parti ad altre applicazioni, usare sempre l'assembly di interoperabilità primario fornito dallo stesso editore della libreria di tipi definita. Oltre a garantire la compatibilità dei tipi, gli assembly di interoperabilità primari vengono spesso personalizzati dal fornitore per migliorare l'interoperabilità.

 Anche se non si prevede di esporre tipi COM di terze parti, l'uso dell'assembly di interoperabilità primario può facilitare l'interazione con i componenti COM. Tuttavia, questa strategia non fornisce alcuna protezione dalle eventuali modifiche apportate da un fornitore ai tipi definiti in un assembly di interoperabilità primario. Quando l'applicazione richiede questo tipo di protezione, generare un proprio assembly di interoperabilità invece di usare l'assembly di interoperabilità primario.

 È necessario registrare tutti gli assembly di interoperabilità primari acquisiti nel computer di sviluppo prima di potervi fare riferimento con Visual Studio. Visual Studio cerca e usa un assembly di interoperabilità primario la prima volta che si fa riferimento un tipo da una libreria di tipi COM. Se Visual Studio non riesce a trovare l'assembly di interoperabilità primario associato alla libreria di tipi, chiede di acquisirlo o propone di creare un altro assembly di interoperabilità. Analogamente, anche l'[utilità di importazione della libreria dei tipi (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) usa il Registro di sistema per trovare gli assembly di interoperabilità primari.

 Anche se non è necessario registrare gli assembly di interoperabilità primari, a meno che non si preveda di usare Visual Studio, la registrazione offre due vantaggi:

- Un assembly di interoperabilità primario registrato è contrassegnato chiaramente in corrispondenza della chiave del Registro di sistema della libreria dei tipi originale. La registrazione è il modo migliore per individuare un assembly di interoperabilità primario nel computer in uso.

- È possibile evitare di generare accidentalmente un nuovo assembly di interoperabilità e di usarlo se, in futuro, si userà Visual Studio per fare riferimento a un tipo per cui si dispone di un assembly di interoperabilità primario non registrato.

Usare lo [strumento di registrazione degli assembly (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) per registrare un assembly di interoperabilità primario.

## <a name="to-register-a-primary-interop-assembly"></a>Per registrare un assembly di interoperabilità primario

1. Al prompt dei comandi digitare:

     **regasm** *nomeassembly*

     In questo comando, *nomeassembly* è il nome file dell'assembly che viene registrato. Regasm.exe aggiunge una voce per l'assembly di interoperabilità primario nella stessa chiave del Registro di sistema della libreria di tipi originale.

## <a name="example"></a>Esempio
 L'esempio seguente registra l'assembly di interoperabilità primario `CompanyA.UtilLib.dll`.

```console
regasm CompanyA.UtilLib.dll
```

## <a name="see-also"></a>Vedere anche

- [Programmazione con assembly di interoperabilità primari](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/baxfadst(v=vs.100))
- [Individuazione di assembly di interoperabilità primari](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/y06sxw56(v=vs.100))
- [Ridistribuzione di assembly di interoperabilità primari](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w0dt2w20(v=vs.100))
