---
title: Interpolazione di stringhe - C# | Microsoft Docs
description: Informazioni sul funzionamento dell&quot;interpolazione di stringhe in C# 6
keywords: .NET, .NET Core, C#, stringa
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 8396be84d229563973011470d0333af017302dc9
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---

<a id="string-interpolation-in-c" class="xliff"></a>

# Interpolazione di stringhe in C# #

Il termine interpolazione di stringhe indica il modo in cui i segnaposto presenti in una stringa vengono sostituiti dal valore di una variabile di tipo stringa. Prima di C# 6, per eseguire questa operazione veniva usato `System.String.Format`. Questa procedura funziona correttamente, ma, poiché usa segnaposto numerati, la scrittura delle istruzioni risulta più complessa e prolissa.

L'interpolazione di stringhe è stata integrata in altri linguaggi di programmazione per un certo periodo di tempo. Ad esempio, in PHP:

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

In C# 6 è stato definito lo stile di interpolazione di stringhe seguente: è possibile usare `$` prima di una stringa per indicare che le variabili e/o le espressioni devono essere sostituite dai i relativi valori.

<a id="prerequisites" class="xliff"></a>

## Prerequisiti
È necessario configurare il computer per l'esecuzione di .NET core. Le istruzioni di installazione sono disponibili nella pagina [.NET Core](https://www.microsoft.com/net/core).
Questa applicazione può essere eseguita in Windows, Ubuntu Linux, macOS o in un contenitore Docker. È necessario installare l'editor di codice preferito. Nelle descrizioni seguenti viene usato [Visual Studio Code](https://code.visualstudio.com/), un editor open source multipiattaforma, ma è possibile usare gli strumenti con cui si ha maggiore familiarità.

<a id="create-the-application" class="xliff"></a>

## Creare l'applicazione

Dopo avere installato tutti gli strumenti, creare una nuova applicazione .NET Core. Per usare il generatore da riga di comando, creare una directory per il progetto, ad esempio `interpolated`, ed eseguire il comando seguente nella shell preferita:

```
dotnet new console
```

Questo comando creerà un progetto .NET di base con un file di progetto, *interpolated.csproj*, e un file di codice sorgente, *Program.cs*. Sarà necessario eseguire `dotnet restore` per ripristinare le dipendenze richieste per la compilazione del progetto.

Per eseguire il programma, usare `dotnet run`. Nella console viene visualizzato "Hello, World".

<a id="intro-to-string-interpolation" class="xliff"></a>

## Introduzione all'interpolazione di stringhe

Con `System.String.Format` vengono specificati i "segnaposto" presenti in una stringa che devono essere sostituiti dai parametri che seguono la stringa stessa. Ad esempio:

[!code-csharp[Esempio di String.Format](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

Verrà visualizzato l'output "My name is Matt Groves".

In C# 6, anziché usare `String.Format`, si definisce una stringa interpolata facendola precedere dal simbolo `$` e quindi usando le variabili direttamente nella stringa. Ad esempio:

[!code-csharp[Esempio di interpolazione](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

Non è necessario usare solo le variabili. È possibile usare qualsiasi espressione inclusa tra parentesi. Ad esempio:

[!code-csharp[Esempio di espressione di interpolazione](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

L'output sarà il seguente:

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

<a id="how-string-interpolation-works" class="xliff"></a>

## Funzionamento dell'interpolazione di stringhe

Nel background, la sintassi dell'interpolazione di stringhe viene convertita in String.Format dal compilatore. Di conseguenza, è possibile eseguire lo [stesso tipo di operazioni eseguite prima con String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).

Ad esempio, è possibile aggiungere spaziatura interna e formattazione numerica:

[!code-csharp[Esempio di formattazione di interpolazione](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

L'output del codice sopra riportato sarà simile a quanto segue:

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

Se un nome di variabile non viene trovato, verrà generato un errore in fase di compilazione.

Ad esempio:

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

Se si compila il codice sopra riportato, verranno generati degli errori:
 
* `Cannot use local variable 'adj' before it is declared`: la variabile `adj` non è stata dichiarata *prima* della stringa interpolata.
* `The name 'otheranimal' does not exist in the current context`: la variabile denominata `otheranimal` non è mai stata dichiarata.

<a id="localization-and-internationalization" class="xliff"></a>

## Localizzazione e internazionalizzazione

Una stringa interpolata supporta `IFormattable` e `FormattableString`, caratteristica utile per l'internazionalizzazione.

Per impostazione predefinita, una stringa interpolata usa le impostazioni cultura correnti. Per usare impostazioni cultura differenti, è possibile eseguire il cast della stringa come `IFormattable`.

Ad esempio:

[!code-csharp[Esempio di internazionalizzazione dell'interpolazione](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

<a id="conclusion" class="xliff"></a>

## Conclusione 

In questa esercitazione è stato illustrato come usare le funzionalità di interpolazione di stringhe di C# 6. Si tratta fondamentalmente di un modo sintetico di scrivere semplici istruzioni `String.Format`, con alcune raccomandazioni per gli usi più avanzati.

