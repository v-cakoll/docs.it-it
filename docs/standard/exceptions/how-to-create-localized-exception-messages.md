---
title: "Procedura: creare eccezioni definite dall'utente con messaggi di eccezione localizzati"
description: Informazioni su come creare eccezioni definite dall'utente con messaggi di eccezione localizzati
author: Youssef1313
ms.author: ronpet
ms.date: 09/13/2019
ms.openlocfilehash: 1e5ef5658e4cb71d0689a1786494eaec57d4e7fb
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332991"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a><span data-ttu-id="35587-103">Procedura: creare eccezioni definite dall'utente con messaggi di eccezione localizzati</span><span class="sxs-lookup"><span data-stu-id="35587-103">How to: create user-defined exceptions with localized exception messages</span></span>

<span data-ttu-id="35587-104">In questo articolo si apprenderà come creare eccezioni definite dall'utente ereditate dalla classe di base <xref:System.Exception> con messaggi di eccezione localizzati tramite assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="35587-104">In this article, you will learn how to create user-defined exceptions that are inherited from the base <xref:System.Exception> class with localized exception messages using satellite assemblies.</span></span>

## <a name="create-custom-exceptions"></a><span data-ttu-id="35587-105">Creare eccezioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="35587-105">Create custom exceptions</span></span>

<span data-ttu-id="35587-106">.NET contiene molte eccezioni diverse che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="35587-106">.NET contains many different exceptions that you can use.</span></span> <span data-ttu-id="35587-107">Tuttavia, in alcuni casi in cui nessuno soddisfa le proprie esigenze, è possibile creare eccezioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="35587-107">However, in some cases when none of them meets your needs, you can create your own custom exceptions.</span></span>

<span data-ttu-id="35587-108">Si supponga di voler creare un `StudentNotFoundException` che contiene una proprietà `StudentName`.</span><span class="sxs-lookup"><span data-stu-id="35587-108">Let's assume you want to create a `StudentNotFoundException` that contains a `StudentName` property.</span></span>
<span data-ttu-id="35587-109">Per creare un'eccezione personalizzata, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="35587-109">To create a custom exception, follow these steps:</span></span>

1. <span data-ttu-id="35587-110">Creare una classe serializzabile che erediti da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="35587-110">Create a serializable class that inherits from <xref:System.Exception>.</span></span> <span data-ttu-id="35587-111">Il nome della classe deve terminare con "Exception":</span><span class="sxs-lookup"><span data-stu-id="35587-111">The class name should end in "Exception":</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception { }
    ```

1. <span data-ttu-id="35587-112">Aggiungere i costruttori predefiniti:</span><span class="sxs-lookup"><span data-stu-id="35587-112">Add the default constructors:</span></span>

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

1. <span data-ttu-id="35587-113">Definire le proprietà e i costruttori aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="35587-113">Define any additional properties and constructors:</span></span>

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

## <a name="create-localized-exception-messages"></a><span data-ttu-id="35587-114">Creare messaggi di eccezione localizzati</span><span class="sxs-lookup"><span data-stu-id="35587-114">Create localized exception messages</span></span>

<span data-ttu-id="35587-115">È stata creata un'eccezione personalizzata, che può essere generata ovunque con codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="35587-115">You have created a custom exception, and you can throw it anywhere with code like the following:</span></span>

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

<span data-ttu-id="35587-116">Il problema con la riga precedente è che "lo studente non è stato trovato".</span><span class="sxs-lookup"><span data-stu-id="35587-116">The problem with the previous line is that "The student cannot be found."</span></span> <span data-ttu-id="35587-117">è solo una stringa costante.</span><span class="sxs-lookup"><span data-stu-id="35587-117">is just a constant string.</span></span> <span data-ttu-id="35587-118">In un'applicazione localizzata è necessario avere messaggi diversi a seconda delle impostazioni cultura dell'utente.</span><span class="sxs-lookup"><span data-stu-id="35587-118">In a localized application, you want to have different messages depending on user culture.</span></span>
<span data-ttu-id="35587-119">Gli [assembly satellite](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) sono un modo efficace per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="35587-119">[Satellite Assemblies](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) are a good way to do that.</span></span> <span data-ttu-id="35587-120">Un assembly satellite è un file con estensione dll che contiene risorse per una lingua specifica.</span><span class="sxs-lookup"><span data-stu-id="35587-120">A satellite assembly is a .dll that contains resources for a specific language.</span></span> <span data-ttu-id="35587-121">Quando si richiede una specifica risorsa in fase di esecuzione, CLR trova tale risorsa a seconda delle impostazioni cultura dell'utente.</span><span class="sxs-lookup"><span data-stu-id="35587-121">When you ask for a specific resources at run time, the CLR finds that resource depending on user culture.</span></span> <span data-ttu-id="35587-122">Se non viene trovato alcun assembly satellite per tali impostazioni cultura, vengono utilizzate le risorse delle impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="35587-122">If no satellite assembly is found for that culture, the resources of the default culture are used.</span></span>

<span data-ttu-id="35587-123">Per creare i messaggi di eccezione localizzati:</span><span class="sxs-lookup"><span data-stu-id="35587-123">To create the localized exception messages:</span></span>

1. <span data-ttu-id="35587-124">Creare una nuova cartella denominata *Resources* per conservare i file di risorse.</span><span class="sxs-lookup"><span data-stu-id="35587-124">Create a new folder named *Resources* to hold the resource files.</span></span>
1. <span data-ttu-id="35587-125">Aggiungere un nuovo file di risorse.</span><span class="sxs-lookup"><span data-stu-id="35587-125">Add a new resource file to it.</span></span> <span data-ttu-id="35587-126">Per eseguire questa operazione in Visual Studio, fare clic con il pulsante destro del mouse sulla cartella in **Esplora soluzioni**e selezionare **Aggiungi** -> **nuovo elemento** -> **file di risorse**.</span><span class="sxs-lookup"><span data-stu-id="35587-126">To do that in Visual Studio, right-click the folder in **Solution Explorer**, and select **Add** -> **New Item** -> **Resources File**.</span></span> <span data-ttu-id="35587-127">Denominare il file *ExceptionMessages. resx*.</span><span class="sxs-lookup"><span data-stu-id="35587-127">Name the file *ExceptionMessages.resx*.</span></span> <span data-ttu-id="35587-128">Questo è il file di risorse predefinito.</span><span class="sxs-lookup"><span data-stu-id="35587-128">This is the default resources file.</span></span>
1. <span data-ttu-id="35587-129">Aggiungere una coppia nome/valore per il messaggio di eccezione, come illustrato nella figura seguente: @no__t 0Add le risorse alle impostazioni cultura predefinite @ no__t-1</span><span class="sxs-lookup"><span data-stu-id="35587-129">Add a name/value pair for your exception message, like the following image shows: ![Add resources to the default culture](media/add-resources-to-default-culture.jpg)</span></span>
1. <span data-ttu-id="35587-130">Aggiungere un nuovo file di risorse per il francese.</span><span class="sxs-lookup"><span data-stu-id="35587-130">Add a new resource file for French.</span></span> <span data-ttu-id="35587-131">Denominarlo *ExceptionMessages.fr-fr. resx*.</span><span class="sxs-lookup"><span data-stu-id="35587-131">Name it *ExceptionMessages.fr-FR.resx*.</span></span>
1. <span data-ttu-id="35587-132">Aggiungere nuovamente una coppia nome/valore per il messaggio di eccezione, ma con un valore francese: @no__t 0Add le risorse per le impostazioni cultura fr-FR @ no__t-1</span><span class="sxs-lookup"><span data-stu-id="35587-132">Add a name/value pair for the exception message again, but with a French value: ![Add resources to the fr-FR culture](media/add-resources-to-fr-culture.jpg)</span></span>
1. <span data-ttu-id="35587-133">Dopo aver compilato il progetto, la cartella di output di compilazione deve contenere la cartella *fr-fr* con un file con estensione *dll* , ovvero l'assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="35587-133">After you build the project, the build output folder should contain the *fr-FR* folder with a *.dll* file, which is the satellite assembly.</span></span>
1. <span data-ttu-id="35587-134">L'eccezione viene generata con codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="35587-134">You throw the exception with code like the following:</span></span>

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QIALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

  > [!NOTE]
  > <span data-ttu-id="35587-135">Se il nome del progetto è `TestProject` e il file di risorse *ExceptionMessages. resx* risiede nella cartella *Resources* del progetto, il nome completo del file di risorse è `TestProject.Resources.ExceptionMessages`.</span><span class="sxs-lookup"><span data-stu-id="35587-135">If the project name is `TestProject` and the resource file *ExceptionMessages.resx* resides in the *Resources* folder of the project, the fully qualified name of the resource file is `TestProject.Resources.ExceptionMessages`.</span></span>

## <a name="see-also"></a><span data-ttu-id="35587-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35587-136">See also</span></span>

- [<span data-ttu-id="35587-137">Come creare eccezioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="35587-137">How to create user-defined exceptions</span></span>](how-to-create-user-defined-exceptions.md)
- [<span data-ttu-id="35587-138">Creazione di assembly satellite per le applicazioni desktop</span><span class="sxs-lookup"><span data-stu-id="35587-138">Creating Satellite Assemblies for Desktop Apps</span></span>](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [<span data-ttu-id="35587-139">base (C# riferimento)</span><span class="sxs-lookup"><span data-stu-id="35587-139">base (C# Reference)</span></span>](../../csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="35587-140">Questo (C# riferimento)</span><span class="sxs-lookup"><span data-stu-id="35587-140">this (C# Reference)</span></span>](../../csharp/language-reference/keywords/this.md)
