---
title: Distribuzione di una applicazione di interoperabilità
description: Distribuire un'applicazione di interoperabilità, che in genere include un assembly client .NET, assembly di interoperabilità di librerie dei tipi COM distinte e componenti COM registrati.
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], interop
- strong-named assemblies, interop applications
- unsigned assemblies
- private assemblies
- exposing COM components to .NET Framework
- interoperation with unmanaged code, deploying applications
- shared assemblies
- COM interop, deploying applications
- interoperation with unmanaged code, exposing COM components
- signed assemblies
- COM interop, exposing COM components
ms.assetid: ea8a403e-ae03-4faa-9d9b-02179ec72992
ms.openlocfilehash: 744307d4175d151d07acbedd5815e538307c8973
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617483"
---
# <a name="deploying-an-interop-application"></a>Distribuzione di una applicazione di interoperabilità
Un'applicazione di interoperabilità in genere include un assembly client .NET, uno o più assembly di interoperabilità che rappresentano librerie dei tipi COM distinte e uno o più componenti COM registrati. Visual Studio e Windows SDK forniscono strumenti per importare e convertire una libreria dei tipi in un assembly di interoperabilità, come illustrato in [Importazione di una libreria dei tipi come assembly](importing-a-type-library-as-an-assembly.md). Un'applicazione di interoperabilità può essere distribuita in due modi:  
  
- Utilizzando i tipi di interoperabilità incorporati: a partire dalla .NET Framework 4, è possibile indicare al compilatore di incorporare le informazioni sui tipi da un assembly di interoperabilità nell'eseguibile. Il compilatore incorpora solo le informazioni sui tipi usate dall'applicazione. Non è necessario distribuire l'assembly di interoperabilità con l'applicazione. Questa è la tecnica consigliata.  
  
- Distribuendo assembly di interoperabilità: è possibile creare un riferimento standard a un assembly di interoperabilità. In questo caso, l'assembly di interoperabilità deve essere distribuito con l'applicazione. Se si ricorre a questa tecnica e non si usa un componente COM privato, fare sempre riferimento all'assembly di interoperabilità primario pubblicato dall'autore del componente COM che si intende incorporare nel codice gestito. Per altre informazioni sulla creazione e sull'uso di assembly di interoperabilità primari, vedere [Primary Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)) (Assembly di interoperabilità primari).  
  
 Se si usano i tipi di interoperabilità incorporati, la distribuzione è estremamente semplice. Non ci sono particolari operazioni da eseguire. Il resto di questo articolo descrive gli scenari di distribuzione degli assembly di interoperabilità con l'applicazione.  
  
## <a name="deploying-interop-assemblies"></a>Distribuzione di assembly di interoperabilità  
 Gli assembly possono avere nomi sicuri. Un assembly con nome sicuro include la chiave pubblica dell'entità di pubblicazione, che fornisce un'identità univoca. Gli assembly prodotti dall'[utilità di importazione della libreria dei tipi (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) possono essere firmati dall'entità di pubblicazione usando l'opzione **/keyfile**. È possibile installare gli assembly firmati nella Global Assembly Cache. Gli assembly non firmati devono essere installati nel computer dell'utente come assembly privati.  
  
### <a name="private-assemblies"></a>Assembly privati  
 Per installare un assembly da usare privatamente, sia l'eseguibile dell'applicazione che l'assembly di interoperabilità contenente i tipi COM importati devono essere installati nella stessa struttura di directory. La figura seguente illustra un assembly di interoperabilità non firmato che verrà usato privatamente da Client1.exe e Client2.exe, che si trovano in directory dell'applicazione separate. L'assembly di interoperabilità, denominato LOANLib.dll in questo esempio, viene installato due volte.  
  
 ![Struttura delle directory e Registro di sistema di Windows](./media/deploying-an-interop-application/com-private-deployment.gif "Struttura delle directory e voci del Registro di sistema per una distribuzione privata")  
  
 Tutti i componenti COM associati all'applicazione devono essere installati nel Registro di sistema di Windows. Se Client1.exe e Client2.exe della figura vengono installati in computer diversi, è necessario registrare i componenti COM in entrambi i computer.  
  
### <a name="shared-assemblies"></a>Assembly condivisi  
 Gli assembli condivisi da più applicazioni devono essere installati in un repository centralizzato denominato Global Assembly Cache. I client .NET possono accedere alla stessa copia dell'assembly di interoperabilità, che viene firmato e installato nella Global Assembly Cache. Per altre informazioni sulla creazione e sull'uso di assembly di interoperabilità primari, vedere [Primary Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)) (Assembly di interoperabilità primari).  
  
## <a name="see-also"></a>Vedere anche

- [Esposizione di componenti COM a .NET Framework](exposing-com-components.md)
- [Importazione di una libreria dei tipi come assembly](importing-a-type-library-as-an-assembly.md)
- [Uso dei tipi COM nel codice gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Compilazione di un progetto di interoperabilità](compiling-an-interop-project.md)
