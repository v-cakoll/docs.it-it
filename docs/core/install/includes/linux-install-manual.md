---
ms.openlocfilehash: e7d35045892c62f759aad5067962ac5c15a9fb8b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602929"
---

Il runtime di .NET Core SDK e .NET Core possono essere installati manualmente dopo il download. Se si installa .NET Core SDK, non è necessario installare il runtime corrispondente. Scaricare prima di tutto una versione binaria per l'SDK o il runtime da uno dei siti seguenti:

- Download di ✔️ [.net 5,0 Preview](https://dotnet.microsoft.com/download/dotnet/5.0)
- Download di ✔️ [.NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ❌[Download di .NET Core 3,0](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- ❌[Download di .NET Core 2,2](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- Download di ✔️ [.NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

Estrarre quindi il file scaricato e usare il `export` comando per impostare le variabili usate da .NET Core e quindi assicurarsi che .NET Core si trovi nel percorso.

Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, scaricare prima di tutto una versione binaria di .NET Core. Quindi, aprire un terminale ed eseguire i comandi seguenti dalla directory in cui è stato salvato il file.

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> I `export` comandi precedenti rendono disponibili solo i comandi di interfaccia della riga di comando di .NET Core per la sessione terminal in cui è stata eseguita.
>
> È possibile modificare il profilo della Shell per aggiungere i comandi in modo permanente. Sono disponibili numerose Shell diverse per Linux e ognuna presenta un profilo diverso. Ad esempio:
>
> - **Shell bash**: *~/. bash_profile*, *~/.bashrc*
> - **Korn Shell**: *~/.KSHRC* o *. profile*
> - **Shell Z**: *~/.zshrc* o *. zprofile*
>
> Modificare il file di origine appropriato per la shell e aggiungere `:$HOME/dotnet` alla fine dell'istruzione esistente `PATH` . Se non `PATH` è inclusa alcuna istruzione, aggiungere una nuova riga con `export PATH=$PATH:$HOME/dotnet` .
>
> Aggiungere anche `export DOTNET_ROOT=$HOME/dotnet` alla fine del file.

Questo approccio consente di installare diverse versioni in posizioni separate e scegliere in modo esplicito quello da usare per l'applicazione.
