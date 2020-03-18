---
title: Organizzare i progetti per .NET Framework e .NET Core
description: Indicazioni per i responsabili di progetti che desiderano compilare la propria soluzione affiancando .NET Framework e .NET Core.
author: conniey
ms.date: 12/07/2018
ms.openlocfilehash: d71cc3102846c08f4e35831921b8cc4ca82f9e1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75777339"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a>Organizzare il progetto per il supporto sia di .NET Framework che di .NET Core

È possibile creare una soluzione che viene compilata sia per .NET Framework che per .NET Core side-by-side. In questo articolo vengono illustrate diverse opzioni di organizzazione del progetto che consentono di raggiungere questo obiettivo. Ecco alcuni scenari tipici da considerare quando si decide come configurare il layout del progetto con .NET Core.Here are some typical scenarios to consider when you're deciding how to set up your project layout with .NET Core. È possibile che l'elenco non includa tutti gli aspetti desiderati. Definire le priorità in base alle esigenze.

- [**Combinare progetti esistenti e progetti .NET Core in singoli progetti**](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  *Vantaggi:*
  - Semplifica il processo di compilazione compilando un singolo progetto anziché più progetti destinati a una piattaforma o una versione di .NET Framework diversa.
  - Semplifica la gestione dei file di origine per i progetti con più target perché è necessario gestire un singolo file di progetto. Quando si aggiungono o rimuovono file di origine, le alternative richiedono la sincronizzazione manuale con gli altri progetti.
  - Genera facilmente un pacchetto NuGet per l'utilizzo.
  - Scrittura di codice per una versione specifica di .NET Framework nelle librerie tramite l'uso di direttive del compilatore.

  *Scenari non supportati:Unsupported scenarios:*
  - Richiede agli sviluppatori di utilizzare Visual Studio 2017 o versione successiva per aprire i progetti esistenti. Per supportare le versioni precedenti di Visual Studio, è opportuno [mantenere i file di progetto in cartelle diverse](#support-vs).

- <a name="support-vs"></a>[**Mantenere separati i progetti esistenti e i nuovi progetti .NET Core**](#keep-existing-projects-and-create-a-net-core-project)

  *Vantaggi:*
  - Supporta lo sviluppo di progetti esistenti per sviluppatori e collaboratori che potrebbero non disporre di Visual Studio 2017 o versione successiva.
  - Diminuisce la possibilità di creare nuovi bug nei progetti esistenti perché non è necessaria alcuna varianza del codice in tali progetti.

## <a name="example"></a>Esempio

Si consideri il repository seguente:

![Progetto esistente](./media/project-structure/existing-project-structure.png)

[**Codice sorgente**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

Di seguito vengono illustrati vari metodi per l'aggiunta del supporto .NET Core per il repository, a seconda dei vincoli e della complessità dei progetti esistenti.

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a>Sostituire i progetti esistenti con un progetto .NET Core con più destinazioni

Riorganizzare il repository in modo che tutti i file * \*con estensione csproj* esistenti vengano rimossi e venga creato un singolo * \** file con estensione csproj destinato a più framework. Questa è una grande opzione, perché un singolo progetto è in grado di compilare per framework diversi. Include anche la possibilità di gestire diverse opzioni di compilazione e dipendenze a seconda del framework di destinazione.

![Creare un file con estensione csproj con più framework come destinazione](./media/project-structure/multi-targeted-project.png)

[**Codice sorgente**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

Modifiche da notare:

- Sostituzione di *packages.config* e *\*.csproj* con un nuovo [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj). I pacchetti NuGet vengono specificati con `<PackageReference> ItemGroup`.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Mantenere i progetti esistenti e creare un progetto .NET Core

Se sono presenti progetti destinati a framework precedenti, è consigliabile lasciare invariati i progetti e usare un progetto .NET Core in modo che sia destinato a framework futuri.

![Progetto .NET Core con un progetto esistente in un'altra cartella](./media/project-structure/separate-projects-same-source.png)

[**Codice sorgente**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

I progetti esistenti e .NET Core vengono mantenuti in cartelle separate. Mantenere i progetti in cartelle separate evita di forzare l'utente ad avere Visual Studio 2017 o versioni successive. È possibile creare una soluzione separata che consente di aprire solo i progetti precedenti.

## <a name="see-also"></a>Vedere anche

- [Documentazione sul porting di .NET Core](index.md)
