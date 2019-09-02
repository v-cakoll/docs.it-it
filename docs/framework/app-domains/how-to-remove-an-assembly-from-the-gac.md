---
title: 'Procedura: Rimuovere un assembly dalla Global Assembly Cache'
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c66df518a259e57498e31877b2f1a78657e05bc
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040821"
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a>Procedura: Rimuovere un assembly dalla Global Assembly Cache

Esistono due modi per rimuovere un assembly dalla Global Assembly Cache (GAC):

- Usando lo [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md). È possibile usare questa opzione per disinstallare gli assembly inseriti nella GAC durante le fasi di sviluppo e test.

- Usando [Windows Installer](/windows/desktop/Msi/windows-installer-portal). È possibile usare questa opzione per disinstallare gli assembly quando si esegue il test dei pacchetti di installazione o per i sistemi di produzione.

### <a name="removing-an-assembly-with-gacutilexe"></a>Rimozione di un assembly con Gacutil.exe

1. Al prompt dei comandi digitare il seguente comando:

    **gacutil –u** \<*nome assembly*>

    In questo comando *nome assembly* è il nome dell'assembly da rimuovere dalla Global Assembly Cache.

    > [!WARNING]
    > Evitare di usare Gacutil.exe per rimuovere assembly nei sistemi di produzione, perché è possibile che un assembly sia ancora richiesto da qualche applicazione. Usare invece Windows Installer che mantiene un conteggio dei riferimenti per ogni assembly installato nella GAC.

 L'esempio seguente rimuove un assembly denominato `hello.dll` dalla Global Assembly Cache.

```
gacutil -u hello
```

### <a name="removing-an-assembly-with-windows-installer"></a>Rimozione di un assembly con Windows Installer

1. In **Programmi e funzionalità** nel **Pannello di controllo** selezionare l'app da disinstallare. Se il pacchetto di installazione ha inserito assembly nella GAC, questi saranno rimossi da Windows Installer se non vengono usati da altre applicazioni.

    > [!NOTE]
    > Windows Installer mantiene un conteggio dei riferimenti per gli assembly installati nella GAC. La rimozione di un assembly dalla Global Assembly Cache avviene solo quando il conteggio dei riferimenti raggiunge zero. Ciò indica che non viene usato da altre applicazioni installate da un pacchetto di Windows Installer.

## <a name="see-also"></a>Vedere anche

- [Uso di assembly e della Global Assembly Cache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)
- [Procedura: Installare un assembly nella Global Assembly Cache](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)
- [Gacutil.exe (strumento Global Assembly Cache)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
