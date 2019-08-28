---
title: Esposizione di componenti .NET Core a COM
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 33574eeac5b1f7aa2067b1974f3f2e68fb22e8ff
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577173"
---
# <a name="exposing-net-core-components-to-com"></a>Esposizione di componenti .NET Core a COM

In .NET Core, il processo di esposizione degli oggetti .NET a COM è stato significativamente semplificato rispetto a .NET Framework. Nel processo seguente viene illustrato come esporre una classe a COM. In questa esercitazione verrà illustrato come:

- Esporre una classe a COM da .NET Core.
- Generare un server COM nell'ambito della creazione della libreria .NET Core.
- Generare automaticamente un manifesto del server affiancato per COM senza Registro di sistema.

## <a name="prerequisites"></a>Prerequisiti

- Installare [.NET Core 3.0 Preview 7 SDK](https://www.microsoft.com/net/core) o una versione più recente.

## <a name="create-the-library"></a>Creare la libreria

Il primo passaggio consiste nel creare la libreria.

1. Creare una nuova cartella ed eseguire `dotnet new classlib` nella cartella.
2. Aprire `Class1.cs`.
3. Aggiungere `using System.Runtime.InteropServices;` all'inizio del file.
4. Creare un'interfaccia denominata `IServer`. Ad esempio: [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]
5. Aggiungere l'attributo `[Guid("<IID>")]` all'interfaccia con il GUID di interfaccia per l'interfaccia COM che si sta implementando. Ad esempio `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`. Si noti che questo GUID deve essere univoco perché è l'unico identificatore di questa interfaccia per COM. In Visual Studio è possibile generare un GUID passando a Strumenti > Crea GUID per aprire lo strumento Crea GUID.
6. Aggiungere l'attributo `[InterfaceType]` all'interfaccia e specificare le interfacce COM di base che l'interfaccia deve implementare.
7. Creare una classe denominata `Server` che implementi `IServer`.
8. Aggiungere l'attributo `[Guid("<CLSID>")]` alla classe con il GUID dell'identificatore di classe per la classe COM che si sta implementando. Ad esempio `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`. Come per il GUID dell'interfaccia, questo GUID deve essere univoco perché è l'unico identificatore di questa interfaccia per COM.
9. Aggiungere l'attributo `[ComVisible(true)]` sia all'interfaccia che alla classe.

> [!IMPORTANT]
> Diversamente da quanto avviene in .NET Framework, .NET Core richiede di specificare il CLSID di qualsiasi classe che si vuole rendere attivabile tramite COM.

## <a name="generate-the-com-host"></a>Generare l'host COM

1. Aprire il file di progetto `.csproj` e aggiungere `<EnableComHosting>true</EnableComHosting>` all'interno di un tag `<PropertyGroup></PropertyGroup>`.
2. Compilare il progetto.

L'output risultante includerà un file `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` e `ProjectName.comhost.dll`.

## <a name="register-the-com-host-for-com"></a>Registrare l'host COM per COM

Aprire un prompt dei comandi con privilegi elevati ed eseguire `regsvr32 ProjectName.comhost.dll`. Tutti gli oggetti .NET esposti verranno così registrati in COM.

## <a name="enabling-regfree-com"></a>Abilitazione di COM RegFree

1. Aprire il file di progetto `.csproj` e aggiungere `<EnableRegFreeCom>true</EnableRegFreeCom>` all'interno di un tag `<PropertyGroup></PropertyGroup>`.
2. Compilare il progetto.

L'output risultante includerà ora anche un file `ProjectName.X.manifest`. Questo file è il manifesto affiancato da usare con COM senza Registro di sistema.

## <a name="sample"></a>Esempio

È disponibile un [esempio di server COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) funzionante nel repository dotnet/samples in GitHub.

## <a name="additional-notes"></a>Note aggiuntive

Diversamente da .NET Framework, in .NET Core non è disponibile alcun supporto per la generazione di una libreria dei tipi COM (TLB) da un assembly .NET Core. Sarà necessario scrivere manualmente un file IDL o un'intestazione C++ per le dichiarazioni native delle interfacce.

Inoltre, il caricamento di .NET Framework e .NET Core nello stesso processo non è supportato e, di conseguenza, il caricamento di un server COM .NET Core in un processo client COM .NET Framework o viceversa non è supportato.
