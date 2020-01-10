---
title: Organizzare i progetti per .NET Framework e .NET Core
description: Indicazioni per i responsabili di progetti che desiderano compilare la propria soluzione affiancando .NET Framework e .NET Core.
author: conniey
ms.date: 12/07/2018
ms.openlocfilehash: d71cc3102846c08f4e35831921b8cc4ca82f9e1b
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777339"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a>Organizzare il progetto per il supporto sia di .NET Framework che di .NET Core

È possibile creare una soluzione che viene compilata sia per .NET Framework sia per .NET Core side-by-side. Questo articolo illustra diverse opzioni di organizzazione del progetto che consentono di raggiungere questo obiettivo. Ecco alcuni scenari tipici da considerare quando si decide come impostare il layout del progetto con .NET Core. È possibile che l'elenco non includa tutti gli aspetti desiderati. Definire le priorità in base alle esigenze.

- [**Combinare progetti esistenti e progetti .NET Core in singoli progetti**](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  *Vantaggi:*
  - Semplifica il processo di compilazione compilando un singolo progetto anziché più progetti destinati a una versione o a una piattaforma di .NET Framework diversa.
  - Semplifica la gestione dei file di origine per progetti con più destinazioni perché è necessario gestire un singolo file di progetto. Quando si aggiungono o si rimuovono i file di origine, le alternative richiedono la sincronizzazione manuale con gli altri progetti.
  - Genera facilmente un pacchetto NuGet per l'utilizzo.
  - Scrittura di codice per una versione specifica di .NET Framework nelle librerie tramite l'uso di direttive del compilatore.

  *Scenari non supportati:*
  - Richiede agli sviluppatori di usare Visual Studio 2017 o una versione successiva per aprire i progetti esistenti. Per supportare le versioni precedenti di Visual Studio, è opportuno [mantenere i file di progetto in cartelle diverse](#support-vs).

- <a name="support-vs"></a>[**Mantenere separati i progetti esistenti e i nuovi progetti .NET Core**](#keep-existing-projects-and-create-a-net-core-project)

  *Vantaggi:*
  - Supporta lo sviluppo di progetti esistenti per sviluppatori e collaboratori che non possono avere Visual Studio 2017 o versione successiva.
  - Riduce la possibilità di creare nuovi bug nei progetti esistenti in quanto non è necessaria alcuna varianza del codice in tali progetti.

## <a name="example"></a>Esempio

Si consideri il repository seguente:

![Progetto esistente](./media/project-structure/existing-project-structure.png)

[**Codice sorgente**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

Di seguito vengono illustrati vari metodi per l'aggiunta del supporto .NET Core per il repository, a seconda dei vincoli e della complessità dei progetti esistenti.

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a>Sostituire i progetti esistenti con un progetto .NET Core con più destinazioni

Riorganizzare il repository in modo che venga rimosso qualsiasi file *\*csproj* esistente e venga creato un singolo file *\*csproj* destinato a più framework. Si tratta di un'opzione eccezionale, perché un singolo progetto è in grado di eseguire la compilazione per Framework diversi. Include anche la possibilità di gestire diverse opzioni di compilazione e dipendenze a seconda del framework di destinazione.

![Creare un csproj destinato a più Framework](./media/project-structure/multi-targeted-project.png)

[**Codice sorgente**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

Modifiche da notare:

- Sostituzione di *packages.config* e *\*.csproj* con un nuovo [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj). I pacchetti NuGet vengono specificati con `<PackageReference> ItemGroup`.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Mantenere i progetti esistenti e creare un progetto .NET Core

Se sono presenti progetti destinati a framework precedenti, è consigliabile lasciare invariati i progetti e usare un progetto .NET Core in modo che sia destinato a framework futuri.

![Progetto .NET Core con un progetto esistente in un'altra cartella](./media/project-structure/separate-projects-same-source.png)

[**Codice sorgente**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

I progetti esistenti e .NET Core vengono mantenuti in cartelle separate. La conservazione di progetti in cartelle separate evita di dover disporre di Visual Studio 2017 o versioni successive. È possibile creare una soluzione separata che consente di aprire solo i progetti precedenti.

## <a name="see-also"></a>Vedere anche

- [Documentazione sulla portabilità di .NET Core](index.md)
