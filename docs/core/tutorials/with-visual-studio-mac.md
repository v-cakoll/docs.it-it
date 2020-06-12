---
title: Creare un'applicazione console .NET Core usando Visual Studio per Mac
description: Informazioni su come creare un'applicazione console .NET Core usando Visual Studio per Mac.
ms.date: 06/02/2020
ms.openlocfilehash: 57f16e510270b7256b285493b1f978101fc11804
ms.sourcegitcommit: f6350c2c542e6edd52d7e9d6667b96d85d810e67
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84717523"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="9d930-103">Esercitazione: creare un'applicazione console .NET Core usando Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="9d930-103">Tutorial: Create a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="9d930-104">In questa esercitazione viene illustrato come creare ed eseguire un'applicazione console .NET Core utilizzando Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="9d930-104">This tutorial shows how to create and run a .NET Core console application using Visual Studio for Mac.</span></span>

> [!NOTE]
> <span data-ttu-id="9d930-105">Microsoft considera di fondamentale importanza i commenti e i suggerimenti degli utenti.</span><span class="sxs-lookup"><span data-stu-id="9d930-105">Your feedback is highly valued.</span></span> <span data-ttu-id="9d930-106">Sono disponibili due modi per comunicare al team di sviluppatori la propria opinione su Visual Studio per Mac:</span><span class="sxs-lookup"><span data-stu-id="9d930-106">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="9d930-107">In Visual Studio per Mac selezionare **Guida**  >  **segnala un problema** dal menu o **segnala un problema** dalla schermata iniziale, che consente di aprire una finestra per la presentazione di un report sui bug.</span><span class="sxs-lookup"><span data-stu-id="9d930-107">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="9d930-108">È possibile tenere traccia dei commenti e dei suggerimenti inviati nel portale della [community di sviluppatori](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="9d930-108">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="9d930-109">Per inviare un suggerimento, scegliere **Guida**dal menu o fornire un suggerimento dalla  >  **Provide a Suggestion** schermata iniziale, che consente di passare alla [pagina Web della community di sviluppatori Visual Studio per Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41). **Provide a Suggestion**</span><span class="sxs-lookup"><span data-stu-id="9d930-109">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d930-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9d930-110">Prerequisites</span></span>

* <span data-ttu-id="9d930-111">[Visual Studio per Mac versione 8,6 o successiva](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="9d930-111">[Visual Studio for Mac version 8.6 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="9d930-112">Selezionare l'opzione per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9d930-112">Select the option to install .NET Core.</span></span> <span data-ttu-id="9d930-113">L'installazione di Novell è facoltativa per lo sviluppo di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9d930-113">Installing Xamarin is optional for .NET Core development.</span></span> <span data-ttu-id="9d930-114">Per altre informazioni, vedere le seguenti risorse:</span><span class="sxs-lookup"><span data-stu-id="9d930-114">For more information, see the following resources:</span></span>

  * <span data-ttu-id="9d930-115">[Esercitazione: installare Visual Studio per Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="9d930-115">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="9d930-116">[Versioni di MacOS supportate](../install/dependencies.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="9d930-116">[Supported macOS versions](../install/dependencies.md?pivots=os-macos).</span></span>
  * <span data-ttu-id="9d930-117">[Versioni di .NET Core supportate da Visual Studio per Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="9d930-117">[.NET Core versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="9d930-118">Creare l'app</span><span class="sxs-lookup"><span data-stu-id="9d930-118">Create the app</span></span>

<span data-ttu-id="9d930-119">Creare un progetto di app console .NET Core denominato "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="9d930-119">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="9d930-120">Avviare Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="9d930-120">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="9d930-121">Selezionare **nuovo** nella finestra di avvio.</span><span class="sxs-lookup"><span data-stu-id="9d930-121">Select **New** in the start window.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Pulsante Nuovo nella schermata iniziale di Visual Studio per Mac":::

1. <span data-ttu-id="9d930-123">Nella finestra di dialogo **nuovo progetto** selezionare **app** nel nodo **Web e console** .</span><span class="sxs-lookup"><span data-stu-id="9d930-123">In the **New Project** dialog, select **App** under the **Web and Console** node.</span></span> <span data-ttu-id="9d930-124">Selezionare il modello **applicazione console** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9d930-124">Select the **Console Application** template, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Nuovo elenco di modelli di progetto":::

1. <span data-ttu-id="9d930-126">Nell'elenco a discesa **Framework di destinazione** della finestra di dialogo **Configura nuova applicazione console** Selezionare **.NET Core 3,1**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9d930-126">In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET Core 3.1**, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/target-framework.png" alt-text="Selezionare il Framework di destinazione":::

1. <span data-ttu-id="9d930-128">Digitare "HelloWorld" per il **nome del progetto**e selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="9d930-128">Type "HelloWorld" for the **Project Name**, and select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Finestra di dialogo di configurazione della nuova applicazione console":::

<span data-ttu-id="9d930-130">Il modello crea una semplice applicazione "Hello World".</span><span class="sxs-lookup"><span data-stu-id="9d930-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="9d930-131">Chiama il <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> metodo per visualizzare "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="9d930-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="9d930-132">nella finestra del terminale.</span><span class="sxs-lookup"><span data-stu-id="9d930-132">in the terminal window.</span></span>

<span data-ttu-id="9d930-133">Il codice del modello definisce una classe, `Program` , con un singolo metodo, `Main` , che accetta una <xref:System.String> matrice come argomento:</span><span class="sxs-lookup"><span data-stu-id="9d930-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="9d930-134">`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9d930-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="9d930-135">Gli eventuali argomenti della riga di comando forniti quando viene avviata l'applicazione sono disponibili nella `args` matrice.</span><span class="sxs-lookup"><span data-stu-id="9d930-135">Any command-line arguments supplied when the application is launched are available in the `args` array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="9d930-136">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="9d930-136">Run the app</span></span>

1. <span data-ttu-id="9d930-137">Premere <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opzione</kbd> + <kbd>comando</kbd> + <kbd>invio</kbd>) per eseguire l'app senza debug.</span><span class="sxs-lookup"><span data-stu-id="9d930-137">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="Il terminale Mostra Hello World!":::

1. <span data-ttu-id="9d930-139">Chiudere la finestra del **terminale** .</span><span class="sxs-lookup"><span data-stu-id="9d930-139">Close the **Terminal** window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="9d930-140">Migliorare l'app</span><span class="sxs-lookup"><span data-stu-id="9d930-140">Enhance the app</span></span>

<span data-ttu-id="9d930-141">Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e all'ora.</span><span class="sxs-lookup"><span data-stu-id="9d930-141">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="9d930-142">In *Program.cs*sostituire il contenuto del `Main` metodo, ovvero la riga che chiama `Console.WriteLine` , con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="9d930-142">In *Program.cs*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="1":::

   <span data-ttu-id="9d930-143">Il codice visualizza "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="9d930-143">This code displays "What is your name?"</span></span> <span data-ttu-id="9d930-144">nella finestra della console e attende che l'utente immetta una stringa seguita dal tasto <kbd>invio</kbd> .</span><span class="sxs-lookup"><span data-stu-id="9d930-144">in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key.</span></span> <span data-ttu-id="9d930-145">Archivia la stringa in una variabile denominata `name` .</span><span class="sxs-lookup"><span data-stu-id="9d930-145">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="9d930-146">Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`.</span><span class="sxs-lookup"><span data-stu-id="9d930-146">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="9d930-147">Infine, questi valori vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="9d930-147">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="9d930-148">L'oggetto `\n` rappresenta un carattere di nuova riga.</span><span class="sxs-lookup"><span data-stu-id="9d930-148">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="9d930-149">Il segno di dollaro ( `$` ) davanti a una stringa consente di inserire espressioni come i nomi delle variabili tra parentesi graffe nella stringa.</span><span class="sxs-lookup"><span data-stu-id="9d930-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="9d930-150">Il valore dell'espressione viene inserito nella stringa al posto dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="9d930-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="9d930-151">Questa sintassi è detta [stringhe interpolate](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="9d930-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="9d930-152">Premere <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opzione</kbd> + <kbd>comando</kbd> + <kbd>invio</kbd>) per eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="9d930-152">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.</span></span>

1. <span data-ttu-id="9d930-153">Per rispondere alla richiesta, immettere un nome e premere <kbd>invio</kbd>.</span><span class="sxs-lookup"><span data-stu-id="9d930-153">Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Il terminale Mostra l'output del programma modificato":::

1. <span data-ttu-id="9d930-155">Chiudere il terminale.</span><span class="sxs-lookup"><span data-stu-id="9d930-155">Close the terminal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9d930-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="9d930-156">Next steps</span></span>

<span data-ttu-id="9d930-157">In questa esercitazione è stata creata un'applicazione console .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9d930-157">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="9d930-158">Nell'esercitazione successiva si esegue il debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="9d930-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9d930-159">Eseguire il debug di un'applicazione console .NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9d930-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio-mac.md)
