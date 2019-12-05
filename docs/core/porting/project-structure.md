---
title: Organizzare i progetti per .NET Framework e .NET Core
description: Indicazioni per i responsabili di progetti che desiderano compilare la propria soluzione affiancando .NET Framework e .NET Core.
author: conniey
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 789f50ffb61b80f590a24bc45693df895b3424f7
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801934"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a>Organizzare il progetto per il supporto sia di .NET Framework che di .NET Core

Informazioni su come creare una soluzione che viene compilata sia per .NET Framework che per .NET Core side-by-side. Vedere le diverse opzioni per organizzare i progetti e poter raggiungere tale obiettivo. Ecco alcuni scenari tipici da considerare quando si decide quale modalità di configurazione del layout di progetto usare con .NET Core. È possibile che l'elenco non includa tutti gli aspetti desiderati. Definire le priorità in base alle esigenze.

- [**Combinare progetti esistenti e progetti .NET Core in singoli progetti**](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  *Vantaggi:*
  - Semplificazione del processo di compilazione mediante la compilazione di un singolo progetto piuttosto che di progetti multipli, ciascuno destinato a una versione o a una piattaforma differente di .NET Framework.
  - Semplificazione della gestione di file di origine per progetti con più destinazioni perché è necessario gestire un unico file di progetto. Quando si aggiungono o rimuovono i file di origine, le alternative richiedono una sincronizzazione manuale di questi file con altri progetti.
  - Generazione semplificata di un pacchetto NuGet per l'utilizzo.
  - Scrittura di codice per una versione specifica di .NET Framework nelle librerie tramite l'uso di direttive del compilatore.

  *Scenari non supportati:*
  - Richiede agli sviluppatori di usare Visual Studio 2017 o una versione successiva per aprire i progetti esistenti. Per supportare le versioni precedenti di Visual Studio, è opportuno [mantenere i file di progetto in cartelle diverse](#support-vs).

- <a name="support-vs"></a>[**Mantenere separati i progetti esistenti e i nuovi progetti .NET Core**](#keep-existing-projects-and-create-a-net-core-project)

  *Vantaggi:*
  - Supporto dello sviluppo sui progetti esistenti per sviluppatori e collaboratori che non possono avere Visual Studio 2017 o versione successiva.
  - Riduzione della possibilità di creazione di nuovi bug nei progetti esistenti in quanto non è necessaria alcuna varianza del codice nei progetti.

## <a name="example"></a>Esempio

Si consideri il repository seguente:

![Progetto esistente](./media/project-structure/existing-project-structure.png)

[**Codice sorgente**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

Di seguito vengono illustrati vari metodi per l'aggiunta del supporto .NET Core per il repository, a seconda dei vincoli e della complessità dei progetti esistenti.

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a>Sostituire i progetti esistenti con un progetto .NET Core con più destinazioni

Riorganizzare il repository in modo che venga rimosso qualsiasi file *\*csproj* esistente e venga creato un singolo file *\*csproj* destinato a più framework. Questa è un'ottima opzione perché consente di compilare un singolo progetto per diversi framework. Include anche la possibilità di gestire diverse opzioni di compilazione e dipendenze a seconda del framework di destinazione.

![Creare un file csproj con più framework di destinazione](./media/project-structure/multi-targeted-project.png)

[**Codice sorgente**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

Modifiche da notare:

- Sostituzione di *packages.config* e *\*.csproj* con un nuovo [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj). I pacchetti NuGet vengono specificati con `<PackageReference> ItemGroup`.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Mantenere i progetti esistenti e creare un progetto .NET Core

Se sono presenti progetti destinati a framework precedenti, è consigliabile lasciare invariati i progetti e usare un progetto .NET Core in modo che sia destinato a framework futuri.

![Progetto .NET Core con un progetto esistente in un'altra cartella](./media/project-structure/separate-projects-same-source.png)

[**Codice sorgente**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

Modifiche da notare:

- I progetti esistenti e .NET Core vengono mantenuti in cartelle separate.
  - La conservazione di progetti in cartelle separate evita di dover disporre di Visual Studio 2017 o versioni successive. È possibile creare una soluzione separata che consente di aprire solo i progetti precedenti.

## <a name="see-also"></a>Vedere anche

- [Documentazione sulla portabilità di .NET Core](index.md)
