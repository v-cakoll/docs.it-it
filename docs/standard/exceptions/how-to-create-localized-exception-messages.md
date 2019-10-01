---
title: "Procedura: Creare eccezioni definite dall'utente con messaggi di eccezione localizzati"
description: Informazioni su come creare eccezioni definite dall'utente con messaggi di eccezione localizzati
author: Youssef1313
ms.author: ronpet
ms.date: 09/13/2019
ms.openlocfilehash: b4aa567fccda9354bc5959d6b9838d678d53abef
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696710"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a><span data-ttu-id="c5dda-103">Procedura: Creare eccezioni definite dall'utente con messaggi di eccezione localizzati</span><span class="sxs-lookup"><span data-stu-id="c5dda-103">How to: create user-defined exceptions with localized exception messages</span></span>

<span data-ttu-id="c5dda-104">In questo articolo si apprenderà come creare eccezioni definite dall'utente ereditate dalla classe di base <xref:System.Exception> con messaggi di eccezione localizzati tramite assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="c5dda-104">In this article, you will learn how to create user-defined exceptions that are inherited from the base <xref:System.Exception> class with localized exception messages using satellite assemblies.</span></span>

## <a name="create-custom-exceptions"></a><span data-ttu-id="c5dda-105">Creare eccezioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c5dda-105">Create custom exceptions</span></span>

<span data-ttu-id="c5dda-106">.NET contiene molte eccezioni diverse che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="c5dda-106">.NET contains many different exceptions that you can use.</span></span> <span data-ttu-id="c5dda-107">Tuttavia, in alcuni casi in cui nessuno soddisfa le proprie esigenze, è possibile creare eccezioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="c5dda-107">However, in some cases when none of them meets your needs, you can create your own custom exceptions.</span></span>

<span data-ttu-id="c5dda-108">Si supponga di voler creare un `StudentNotFoundException` che contiene una proprietà `StudentName`.</span><span class="sxs-lookup"><span data-stu-id="c5dda-108">Let's assume you want to create a `StudentNotFoundException` that contains a `StudentName` property.</span></span>
<span data-ttu-id="c5dda-109">Per creare un'eccezione personalizzata, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c5dda-109">To create a custom exception, follow these steps:</span></span>

1. <span data-ttu-id="c5dda-110">Creare una classe serializzabile che erediti da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="c5dda-110">Create a serializable class that inherits from <xref:System.Exception>.</span></span> <span data-ttu-id="c5dda-111">Il nome della classe deve terminare con "Exception":</span><span class="sxs-lookup"><span data-stu-id="c5dda-111">The class name should end in "Exception":</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception { }
    ```

1. <span data-ttu-id="c5dda-112">Aggiungere i costruttori predefiniti:</span><span class="sxs-lookup"><span data-stu-id="c5dda-112">Add the default constructors:</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }
    }
    ```

1. <span data-ttu-id="c5dda-113">Definire le proprietà e i costruttori aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="c5dda-113">Define any additional properties and constructors:</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public string StudentName { get; }

        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }

        public StudentNotFoundException(string message, string studentName)
            : this(message)
        {
            StudentName = studentName;
        }
    }
    ```

## <a name="create-localized-exception-messages"></a><span data-ttu-id="c5dda-114">Creare messaggi di eccezione localizzati</span><span class="sxs-lookup"><span data-stu-id="c5dda-114">Create localized exception messages</span></span>

<span data-ttu-id="c5dda-115">È stata creata un'eccezione personalizzata, che può essere generata ovunque con codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c5dda-115">You have created a custom exception, and you can throw it anywhere with code like the following:</span></span>

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

<span data-ttu-id="c5dda-116">Il problema con la riga precedente è che `"The student cannot be found."` è semplicemente una stringa costante.</span><span class="sxs-lookup"><span data-stu-id="c5dda-116">The problem with the previous line is that `"The student cannot be found."` is just a constant string.</span></span> <span data-ttu-id="c5dda-117">In un'applicazione localizzata è necessario avere messaggi diversi a seconda delle impostazioni cultura dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c5dda-117">In a localized application, you want to have different messages depending on user culture.</span></span>
<span data-ttu-id="c5dda-118">Gli [assembly satellite](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) sono un modo efficace per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="c5dda-118">[Satellite Assemblies](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) are a good way to do that.</span></span> <span data-ttu-id="c5dda-119">Un assembly satellite è un file con estensione dll che contiene risorse per una lingua specifica.</span><span class="sxs-lookup"><span data-stu-id="c5dda-119">A satellite assembly is a .dll that contains resources for a specific language.</span></span> <span data-ttu-id="c5dda-120">Quando si richiede una specifica risorsa in fase di esecuzione, CLR trova tale risorsa a seconda delle impostazioni cultura dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c5dda-120">When you ask for a specific resources at run time, the CLR finds that resource depending on user culture.</span></span> <span data-ttu-id="c5dda-121">Se non viene trovato alcun assembly satellite per tali impostazioni cultura, vengono utilizzate le risorse delle impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="c5dda-121">If no satellite assembly is found for that culture, the resources of the default culture are used.</span></span>

<span data-ttu-id="c5dda-122">Per creare i messaggi di eccezione localizzati:</span><span class="sxs-lookup"><span data-stu-id="c5dda-122">To create the localized exception messages:</span></span>

1. <span data-ttu-id="c5dda-123">Creare una nuova cartella denominata *Resources* per conservare i file di risorse.</span><span class="sxs-lookup"><span data-stu-id="c5dda-123">Create a new folder named *Resources* to hold the resource files.</span></span>
1. <span data-ttu-id="c5dda-124">Aggiungere un nuovo file di risorse.</span><span class="sxs-lookup"><span data-stu-id="c5dda-124">Add a new resource file to it.</span></span> <span data-ttu-id="c5dda-125">Per eseguire questa operazione in Visual Studio, fare clic con il pulsante destro del mouse sulla cartella in **Esplora soluzioni**e selezionare **Aggiungi** > **nuovo elemento** > **file di risorse**.</span><span class="sxs-lookup"><span data-stu-id="c5dda-125">To do that in Visual Studio, right-click the folder in **Solution Explorer**, and select **Add** > **New Item** > **Resources File**.</span></span> <span data-ttu-id="c5dda-126">Denominare il file *ExceptionMessages. resx*.</span><span class="sxs-lookup"><span data-stu-id="c5dda-126">Name the file *ExceptionMessages.resx*.</span></span> <span data-ttu-id="c5dda-127">Questo è il file di risorse predefinito.</span><span class="sxs-lookup"><span data-stu-id="c5dda-127">This is the default resources file.</span></span>
1. <span data-ttu-id="c5dda-128">Aggiungere una coppia nome/valore per il messaggio di eccezione, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="c5dda-128">Add a name/value pair for your exception message, like the following image shows:</span></span>

   ![Aggiungere risorse alle impostazioni cultura predefinite](media/add-resources-to-default-culture.jpg)

1. <span data-ttu-id="c5dda-130">Aggiungere un nuovo file di risorse per il francese.</span><span class="sxs-lookup"><span data-stu-id="c5dda-130">Add a new resource file for French.</span></span> <span data-ttu-id="c5dda-131">Denominarlo *ExceptionMessages.fr-fr. resx*.</span><span class="sxs-lookup"><span data-stu-id="c5dda-131">Name it *ExceptionMessages.fr-FR.resx*.</span></span>
1. <span data-ttu-id="c5dda-132">Aggiungere nuovamente una coppia nome/valore per il messaggio di eccezione, ma con un valore francese:</span><span class="sxs-lookup"><span data-stu-id="c5dda-132">Add a name/value pair for the exception message again, but with a French value:</span></span>

   ![Aggiungere risorse alle impostazioni cultura fr-FR](media/add-resources-to-fr-culture.jpg)

1. <span data-ttu-id="c5dda-134">Dopo aver compilato il progetto, la cartella di output di compilazione deve contenere la cartella *fr-fr* con un file con estensione *dll* , ovvero l'assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="c5dda-134">After you build the project, the build output folder should contain the *fr-FR* folder with a *.dll* file, which is the satellite assembly.</span></span>
1. <span data-ttu-id="c5dda-135">L'eccezione viene generata con codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c5dda-135">You throw the exception with code like the following:</span></span>

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QIALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

  > [!NOTE]
  > <span data-ttu-id="c5dda-136">Se il nome del progetto è `TestProject` e il file di risorse *ExceptionMessages. resx* risiede nella cartella *Resources* del progetto, il nome completo del file di risorse è `TestProject.Resources.ExceptionMessages`.</span><span class="sxs-lookup"><span data-stu-id="c5dda-136">If the project name is `TestProject` and the resource file *ExceptionMessages.resx* resides in the *Resources* folder of the project, the fully qualified name of the resource file is `TestProject.Resources.ExceptionMessages`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5dda-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5dda-137">See also</span></span>

- [<span data-ttu-id="c5dda-138">Come creare eccezioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="c5dda-138">How to create user-defined exceptions</span></span>](how-to-create-user-defined-exceptions.md)
- [<span data-ttu-id="c5dda-139">Creazione di assembly satellite per le applicazioni desktop</span><span class="sxs-lookup"><span data-stu-id="c5dda-139">Creating Satellite Assemblies for Desktop Apps</span></span>](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [<span data-ttu-id="c5dda-140">base (C# riferimento)</span><span class="sxs-lookup"><span data-stu-id="c5dda-140">base (C# Reference)</span></span>](../../csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="c5dda-141">Questo (C# riferimento)</span><span class="sxs-lookup"><span data-stu-id="c5dda-141">this (C# Reference)</span></span>](../../csharp/language-reference/keywords/this.md)
