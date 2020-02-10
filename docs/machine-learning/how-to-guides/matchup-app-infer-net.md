---
title: Infer.NET gioco-up app-programmazione probabilistica
description: Scopri come usare la programmazione probabilistica con Infer.NET per creare un'app per elenchi di corrispondenze di gioco basata su una versione semplificata di TrueSkill.
ms.date: 01/30/2020
ms.custom: mvc,how-to
ms.openlocfilehash: 8e489d61c5e6cca53ba12b13fddd0b73c7f85ef9
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092603"
---
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a>Creare un'app elenco di corrispondenze di gioco con Infer.NET e la programmazione probabilistica

Questa guida pratica descrive la programmazione probabilistica tramite Infer.NET. La programmazione probabilistica è un approccio di apprendimento automatico in cui modelli personalizzati vengono espressi come programmi. Permette di integrare informazioni specifiche di un dominio nei modelli e rendere il sistema di apprendimento automatico maggiormente interpretabile. Supporta anche l'inferenza online, ovvero il processo di apprendere man mano che arrivano nuovi dati. Infer.NET viene usato in diversi prodotti Microsoft, tra cui Azure, Xbox e Bing.

## <a name="what-is-probabilistic-programming"></a>Che cos'è la programmazione probabilistica?

La programmazione probabilistica permette di creare modelli statistici di processi reali.

## <a name="prerequisites"></a>Prerequisites

- Configurazione di un ambiente di sviluppo locale

  Questa guida pratica presuppone la presenza di un computer che possa essere usato per lo sviluppo. L'esercitazione .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene le istruzioni per configurare l'ambiente di sviluppo locale in MacOS, Windows o Linux.

## <a name="create-your-app"></a>Creare l'app

1. Aprire un nuovo prompt dei comandi ed eseguire i comandi seguenti:

```dotnetcli
dotnet new console -o myApp
cd myApp
```

Il comando `dotnet` crea un'applicazione `new` di tipo `console`. Il parametro `-o` crea una directory denominata `myApp` in cui viene archiviata l'app, popolata con i file necessari. Il comando `cd myApp` permette di passare alla directory dell'app appena creata.

## <a name="install-infernet-package"></a>Installare il pacchetto Infer.NET

Per usare Infer.NET, è necessario installare il pacchetto `Microsoft.ML.Probabilistic.Compiler`. Al prompt dei comandi eseguire il comando seguente:

```dotnetcli
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a>Progettare il modello

L'esempio usa partite di ping pong o calcio giocate in ufficio. Sono disponibili i partecipanti e il risultato di ogni partita.  Si vogliono dedurre le abilità del giocatore da questi dati. Presupporre che ogni giocatore abbia un'abilità latente normalmente distribuita e che le sue prestazioni in una partita specifica siano una versione accentuata di questa abilità. I dati vincolano le prestazioni del vincitore come migliori delle prestazioni del giocatore sconfitto. Si tratta di una versione semplificata del celebre modello [TrueSkill](https://www.microsoft.com/research/project/trueskill-ranking-system/), che supporta anche squadre, pareggi e altre estensioni. Una [versione avanzata](https://www.microsoft.com/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) di questo modello viene usata per il matchmaking nei vendutissimi titoli Halo e Gears of War.

È necessario elencare le abilità del giocatore dedotte, insieme alla rispettiva varianza, ovvero la misura di incertezza riguardo alle abilità.

*Dati di esempio dei risultati di gioco*

Game |Vincitori | Sconfitti
---------|----------|---------
 1 | Giocatore 0 | Giocatore 1
 2 | Giocatore 0 | Giocatore 3
 3 | Giocatore 0 | Giocatore 4
 4 | Giocatore 1 | Giocatore 2
 5 | Giocatore 3 | Giocatore 1
 6 | Giocatore 4 | Giocatore 2

Osservando più attentamente i dati di esempio, si noterà che i giocatori 3 e 4 hanno entrambi una vittoria e una sconfitta. Si osserveranno ora le classificazioni usando la programmazione probabilistica. Si noti anche la presenza di un giocatore 0, perché gli elenchi di corrispondenze sono in base zero per gli sviluppatori.

## <a name="write-some-code"></a>Scrivere codice

Dopo aver progettato il modello, è possibile esprimerlo come programma probabilistico tramite l'API di modellazione Infer.NET. Aprire `Program.cs` nell'editor di testo preferito e sostituire tutto il contenuto con il codice seguente:

```csharp
namespace myApp

{
    using System;
    using System.Linq;
    using Microsoft.ML.Probabilistic;
    using Microsoft.ML.Probabilistic.Distributions;
    using Microsoft.ML.Probabilistic.Models;

    class Program
    {

        static void Main(string[] args)
        {
            // The winner and loser in each of 6 samples games
            var winnerData = new[] { 0, 0, 0, 1, 3, 4 };
            var loserData = new[] { 1, 3, 4, 2, 1, 2 };

            // Define the statistical model as a probabilistic program
            var game = new Range(winnerData.Length);
            var player = new Range(winnerData.Concat(loserData).Max() + 1);
            var playerSkills = Variable.Array<double>(player);
            playerSkills[player] = Variable.GaussianFromMeanAndVariance(6, 9).ForEach(player);

            var winners = Variable.Array<int>(game);
            var losers = Variable.Array<int>(game);

            using (Variable.ForEach(game))
            {
                // The player performance is a noisy version of their skill
                var winnerPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[winners[game]], 1.0);
                var loserPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[losers[game]], 1.0);

                // The winner performed better in this game
                Variable.ConstrainTrue(winnerPerformance > loserPerformance);
            }

            // Attach the data to the model
            winners.ObservedValue = winnerData;
            losers.ObservedValue = loserData;

            // Run inference
            var inferenceEngine = new InferenceEngine();
            var inferredSkills = inferenceEngine.Infer<Gaussian[]>(playerSkills);

            // The inferred skills are uncertain, which is captured in their variance
            var orderedPlayerSkills = inferredSkills
               .Select((s, i) => new { Player = i, Skill = s })
               .OrderByDescending(ps => ps.Skill.GetMean());

            foreach (var playerSkill in orderedPlayerSkills)
            {
                Console.WriteLine($"Player {playerSkill.Player} skill: {playerSkill.Skill}");
            }
        }
    }
}
```

## <a name="run-your-app"></a>Eseguire l'app

Al prompt dei comandi eseguire il comando seguente:

```dotnetcli
dotnet run
```

## <a name="results"></a>Risultati

I risultati saranno simili ai seguenti:

```console
Compiling model...done.
Iterating:
.........|.........|.........|.........|.........| 50
Player 0 skill: Gaussian(9.517, 3.926)
Player 3 skill: Gaussian(6.834, 3.892)
Player 4 skill: Gaussian(6.054, 4.731)
Player 1 skill: Gaussian(4.955, 3.503)
Player 2 skill: Gaussian(2.639, 4.288)
```

Nei risultati si noti che in base al modello il giocatore 3 è in posizione leggermente superiore rispetto al giocatore 4. Il motivo è che la vittoria del giocatore 3 sul giocatore 1 è più significativa rispetto alla vittoria del giocatore 4 sul giocatore 2: notare infatti che il giocatore 1 batte il giocatore 2. Il giocatore 0 è il campione assoluto.

## <a name="keep-learning"></a>Per continuare ad apprendere

La progettazione di modelli statistici è una competenza di per sé. Il team di Microsoft Research Cambridge ha redatto un [libro online gratuito](http://mbmlbook.com/), che offre una pratica introduzione all'articolo. Il capitolo 3 di questo libro descrive più dettagliatamente il modello TrueSkill. Dopo aver ideato un modello, è possibile trasformarlo in codice usando la [vasta documentazione](https://dotnet.github.io/infer/) nel sito Web Infer.NET.

## <a name="next-steps"></a>Passaggi successivi

Visitare il repository GitHub per Infer.NET per continuare ad acquisire familiarità e trovare altri esempi.
> [!div class="nextstepaction"]
> [Repository GitHub dotnet/infer](https://github.com/dotnet/infer)
