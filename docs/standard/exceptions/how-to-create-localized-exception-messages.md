---
title: Come creare eccezioni definite dall'utente con messaggi di eccezione localizzatiHow to create user-defined exceptions with localized exception messages
description: Informazioni su come creare eccezioni definite dall'utente con messaggi di eccezione localizzati
author: Youssef1313
dev_langs:
- csharp
- vb
ms.date: 09/13/2019
ms.openlocfilehash: 5a02c71b16e2c8e5ade5128866af7dc46a03ba4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160183"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a><span data-ttu-id="02513-103">Come creare eccezioni definite dall'utente con messaggi di eccezione localizzatiHow to create user-defined exceptions with localized exception messages</span><span class="sxs-lookup"><span data-stu-id="02513-103">How to create user-defined exceptions with localized exception messages</span></span>

<span data-ttu-id="02513-104">In questo articolo verrà illustrato come creare eccezioni definite dall'utente <xref:System.Exception> ereditate dalla classe base con messaggi di eccezione localizzati tramite assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="02513-104">In this article, you will learn how to create user-defined exceptions that are inherited from the base <xref:System.Exception> class with localized exception messages using satellite assemblies.</span></span>

## <a name="create-custom-exceptions"></a><span data-ttu-id="02513-105">Creare eccezioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="02513-105">Create custom exceptions</span></span>

<span data-ttu-id="02513-106">.NET contiene molte eccezioni diverse che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="02513-106">.NET contains many different exceptions that you can use.</span></span> <span data-ttu-id="02513-107">Tuttavia, in alcuni casi quando nessuno di essi soddisfa le proprie esigenze, è possibile creare eccezioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="02513-107">However, in some cases when none of them meets your needs, you can create your own custom exceptions.</span></span>

<span data-ttu-id="02513-108">Si supponga di voler creare `StudentNotFoundException` un `StudentName` che contiene una proprietà.</span><span class="sxs-lookup"><span data-stu-id="02513-108">Let's assume you want to create a `StudentNotFoundException` that contains a `StudentName` property.</span></span>
<span data-ttu-id="02513-109">Per creare un'eccezione personalizzata, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="02513-109">To create a custom exception, follow these steps:</span></span>

1. <span data-ttu-id="02513-110">Creare una classe serializzabile che <xref:System.Exception>eredita da .</span><span class="sxs-lookup"><span data-stu-id="02513-110">Create a serializable class that inherits from <xref:System.Exception>.</span></span> <span data-ttu-id="02513-111">Il nome della classe deve terminare con "Exception":</span><span class="sxs-lookup"><span data-stu-id="02513-111">The class name should end in "Exception":</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception { }
    ```

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception
    End Class
    ```

1. <span data-ttu-id="02513-112">Aggiungere i costruttori predefiniti:Add the default constructors:</span><span class="sxs-lookup"><span data-stu-id="02513-112">Add the default constructors:</span></span>

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

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception

        Public Sub New()
        End Sub

        Public Sub New(message As String)
            MyBase.New(message)
        End Sub

        Public Sub New(message As String, inner As Exception)
            MyBase.New(message, inner)
        End Sub
    End Class
    ```

1. <span data-ttu-id="02513-113">Definire eventuali proprietà e costruttori aggiuntivi:Define any additional properties and constructors:</span><span class="sxs-lookup"><span data-stu-id="02513-113">Define any additional properties and constructors:</span></span>

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

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception

        Public ReadOnly Property StudentName As String

        Public Sub New()
        End Sub

        Public Sub New(message As String)
            MyBase.New(message)
        End Sub

        Public Sub New(message As String, inner As Exception)
            MyBase.New(message, inner)
        End Sub

        Public Sub New(message As String, studentName As String)
            Me.New(message)
            StudentName = studentName
        End Sub
    End Class
    ```

## <a name="create-localized-exception-messages"></a><span data-ttu-id="02513-114">Creare messaggi di eccezione localizzatiCreate localized exception messages</span><span class="sxs-lookup"><span data-stu-id="02513-114">Create localized exception messages</span></span>

<span data-ttu-id="02513-115">È stata creata un'eccezione personalizzata ed è possibile generarla ovunque con codice simile al seguente:You have created a custom exception, and you can throw it anywhere with code like the following:</span><span class="sxs-lookup"><span data-stu-id="02513-115">You have created a custom exception, and you can throw it anywhere with code like the following:</span></span>

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

```vb
Throw New StudentNotFoundException("The student cannot be found.", "John")
```

<span data-ttu-id="02513-116">Il problema con la `"The student cannot be found."` riga precedente è che è solo una stringa costante.</span><span class="sxs-lookup"><span data-stu-id="02513-116">The problem with the previous line is that `"The student cannot be found."` is just a constant string.</span></span> <span data-ttu-id="02513-117">In un'applicazione localizzata, si desidera avere messaggi diversi a seconda delle impostazioni cultura dell'utente.</span><span class="sxs-lookup"><span data-stu-id="02513-117">In a localized application, you want to have different messages depending on user culture.</span></span>
<span data-ttu-id="02513-118">[Gli assembly satellitari](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) sono un buon modo per farlo.</span><span class="sxs-lookup"><span data-stu-id="02513-118">[Satellite Assemblies](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) are a good way to do that.</span></span> <span data-ttu-id="02513-119">Un assembly satellite è una DLL che contiene risorse per una lingua specifica.</span><span class="sxs-lookup"><span data-stu-id="02513-119">A satellite assembly is a .dll that contains resources for a specific language.</span></span> <span data-ttu-id="02513-120">Quando si richiede una risorsa specifica in fase di esecuzione, CLR trova tale risorsa in base alle impostazioni cultura dell'utente.</span><span class="sxs-lookup"><span data-stu-id="02513-120">When you ask for a specific resources at run time, the CLR finds that resource depending on user culture.</span></span> <span data-ttu-id="02513-121">Se non viene trovato alcun assembly satellite per tali impostazioni cultura, vengono utilizzate le risorse delle impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="02513-121">If no satellite assembly is found for that culture, the resources of the default culture are used.</span></span>

<span data-ttu-id="02513-122">Per creare i messaggi di eccezione localizzati:</span><span class="sxs-lookup"><span data-stu-id="02513-122">To create the localized exception messages:</span></span>

1. <span data-ttu-id="02513-123">Creare una nuova cartella denominata *Resources* per contenere i file di risorse.</span><span class="sxs-lookup"><span data-stu-id="02513-123">Create a new folder named *Resources* to hold the resource files.</span></span>
1. <span data-ttu-id="02513-124">Aggiungere un nuovo file di risorse.</span><span class="sxs-lookup"><span data-stu-id="02513-124">Add a new resource file to it.</span></span> <span data-ttu-id="02513-125">A tale scopo in Visual Studio, fare clic con il pulsante destro del mouse sulla cartella in **Esplora soluzioni**e scegliere **Aggiungi** > **nuovo file** > **di risorse**elemento .</span><span class="sxs-lookup"><span data-stu-id="02513-125">To do that in Visual Studio, right-click the folder in **Solution Explorer**, and select **Add** > **New Item** > **Resources File**.</span></span> <span data-ttu-id="02513-126">Assegnare al file il nome *ExceptionMessages.resx*.</span><span class="sxs-lookup"><span data-stu-id="02513-126">Name the file *ExceptionMessages.resx*.</span></span> <span data-ttu-id="02513-127">Questo è il file di risorse predefinito.</span><span class="sxs-lookup"><span data-stu-id="02513-127">This is the default resources file.</span></span>
1. <span data-ttu-id="02513-128">Aggiungere una coppia nome/valore per il messaggio di eccezione, come illustrato nell'immagine seguente:Add a name/value pair for your exception message, like the following image shows:</span><span class="sxs-lookup"><span data-stu-id="02513-128">Add a name/value pair for your exception message, like the following image shows:</span></span>

   ![Aggiungere risorse alle impostazioni cultura predefiniteAdd resources to the default culture](media/add-resources-to-default-culture.jpg)

1. <span data-ttu-id="02513-130">Aggiungere un nuovo file di risorse per il francese.</span><span class="sxs-lookup"><span data-stu-id="02513-130">Add a new resource file for French.</span></span> <span data-ttu-id="02513-131">Denominarlo *ExceptionMessages.fr-FR.resx*.</span><span class="sxs-lookup"><span data-stu-id="02513-131">Name it *ExceptionMessages.fr-FR.resx*.</span></span>
1. <span data-ttu-id="02513-132">Aggiungere nuovamente una coppia nome/valore per il messaggio di eccezione, ma con un valore francese:Add a name/value pair for the exception message again, but with a French value:</span><span class="sxs-lookup"><span data-stu-id="02513-132">Add a name/value pair for the exception message again, but with a French value:</span></span>

   ![Aggiungere risorse alle impostazioni cultura fr-FR](media/add-resources-to-fr-culture.jpg)

1. <span data-ttu-id="02513-134">Dopo aver compilato il progetto, la cartella dell'output di compilazione deve contenere la cartella *fr-FR* con un file *DLL,* ovvero l'assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="02513-134">After you build the project, the build output folder should contain the *fr-FR* folder with a *.dll* file, which is the satellite assembly.</span></span>
1. <span data-ttu-id="02513-135">Generare l'eccezione con codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="02513-135">You throw the exception with code like the following:</span></span>

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QIALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

    ```vb
    Dim resourceManager As New ResourceManager("FULLY_QIALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly())
    Throw New StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John")
    ```

    > [!NOTE]
    > <span data-ttu-id="02513-136">Se il nome `TestProject` del progetto è e il file di risorse *ExceptionMessages.resx* si trova nella `TestProject.Resources.ExceptionMessages`cartella *Resources* del progetto, il nome completo del file di risorse è .</span><span class="sxs-lookup"><span data-stu-id="02513-136">If the project name is `TestProject` and the resource file *ExceptionMessages.resx* resides in the *Resources* folder of the project, the fully qualified name of the resource file is `TestProject.Resources.ExceptionMessages`.</span></span>

## <a name="see-also"></a><span data-ttu-id="02513-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02513-137">See also</span></span>

- [<span data-ttu-id="02513-138">Come creare eccezioni definite dall'utenteHow to create user-defined exceptions</span><span class="sxs-lookup"><span data-stu-id="02513-138">How to create user-defined exceptions</span></span>](how-to-create-user-defined-exceptions.md)
- [<span data-ttu-id="02513-139">Creazione di assembly satellite per applicazioni desktop</span><span class="sxs-lookup"><span data-stu-id="02513-139">Creating Satellite Assemblies for Desktop Apps</span></span>](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [<span data-ttu-id="02513-140">base (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="02513-140">base (C# Reference)</span></span>](../../csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="02513-141">this (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="02513-141">this (C# Reference)</span></span>](../../csharp/language-reference/keywords/this.md)
