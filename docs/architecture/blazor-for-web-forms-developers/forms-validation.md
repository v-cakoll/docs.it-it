---
title: Moduli e convalida
description: Informazioni su come compilare moduli con la convalida lato client in Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- Blazor WebAssembly
ms.date: 09/19/2019
ms.openlocfilehash: 1a99719f59415872510aef051d1f3c73daf53e15
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173276"
---
# <a name="forms-and-validation"></a><span data-ttu-id="969b5-103">Moduli e convalida</span><span class="sxs-lookup"><span data-stu-id="969b5-103">Forms and validation</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="969b5-104">Il framework Web Form ASP.NET include un set di controlli server di convalida che gestiscono la convalida dell'input utente immesso in un modulo ( `RequiredFieldValidator` ,, `CompareValidator` `RangeValidator` e così via).</span><span class="sxs-lookup"><span data-stu-id="969b5-104">The ASP.NET Web Forms framework includes a set of validation server controls that handle validating user input entered into a form (`RequiredFieldValidator`, `CompareValidator`, `RangeValidator`, and so on).</span></span> <span data-ttu-id="969b5-105">Il framework Web Form ASP.NET supporta anche l'associazione di modelli e la convalida del modello in base alle annotazioni dei dati ( `[Required]` ,, `[StringLength]` `[Range]` e così via).</span><span class="sxs-lookup"><span data-stu-id="969b5-105">The ASP.NET Web Forms framework also supports model binding and validating the model based on data annotations (`[Required]`, `[StringLength]`, `[Range]`, and so on).</span></span> <span data-ttu-id="969b5-106">La logica di convalida può essere applicata sia nel server che nel client usando la convalida basata su JavaScript non intrusiva.</span><span class="sxs-lookup"><span data-stu-id="969b5-106">The validation logic can be enforced both on the server and on the client using unobtrusive JavaScript-based validation.</span></span> <span data-ttu-id="969b5-107">Il `ValidationSummary` controllo server viene utilizzato per visualizzare un riepilogo degli errori di convalida per l'utente.</span><span class="sxs-lookup"><span data-stu-id="969b5-107">The `ValidationSummary` server control is used to display a summary of the validation errors to the user.</span></span>

Blazor<span data-ttu-id="969b5-108">supporta la condivisione della logica di convalida tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="969b5-108"> supports the sharing of validation logic between both the client and the server.</span></span> <span data-ttu-id="969b5-109">ASP.NET fornisce implementazioni JavaScript predefinite di molte convalide server comuni.</span><span class="sxs-lookup"><span data-stu-id="969b5-109">ASP.NET provides pre-built JavaScript implementations of many common server validations.</span></span> <span data-ttu-id="969b5-110">In molti casi, lo sviluppatore deve ancora scrivere codice JavaScript per implementare completamente la logica di convalida specifica dell'app.</span><span class="sxs-lookup"><span data-stu-id="969b5-110">In many cases, the developer still has to write JavaScript to fully implement their app-specific validation logic.</span></span> <span data-ttu-id="969b5-111">Gli stessi tipi di modello, le annotazioni dei dati e la logica di convalida possono essere utilizzati sia sul server che sul client.</span><span class="sxs-lookup"><span data-stu-id="969b5-111">The same model types, data annotations, and validation logic can be used on both the server and client.</span></span>

Blazor<span data-ttu-id="969b5-112">fornisce un set di componenti di input.</span><span class="sxs-lookup"><span data-stu-id="969b5-112"> provides a set of input components.</span></span> <span data-ttu-id="969b5-113">I componenti di input gestiscono i dati dei campi di associazione a un modello e convalidano l'input dell'utente quando viene inviato il modulo.</span><span class="sxs-lookup"><span data-stu-id="969b5-113">The input components handle binding field data to a model and validating the user input when the form is submitted.</span></span>

|<span data-ttu-id="969b5-114">Componente di input</span><span class="sxs-lookup"><span data-stu-id="969b5-114">Input component</span></span>|<span data-ttu-id="969b5-115">Elemento HTML sottoposto a rendering</span><span class="sxs-lookup"><span data-stu-id="969b5-115">Rendered HTML element</span></span>    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

<span data-ttu-id="969b5-116">Il `EditForm` componente esegue il wrapping di questi componenti di input e orchestra il processo di convalida tramite un `EditContext` .</span><span class="sxs-lookup"><span data-stu-id="969b5-116">The `EditForm` component wraps these input components and orchestrates the validation process through an `EditContext`.</span></span> <span data-ttu-id="969b5-117">Quando si crea un oggetto `EditForm` , è necessario specificare l'istanza del modello da associare a utilizzando il `Model` parametro.</span><span class="sxs-lookup"><span data-stu-id="969b5-117">When creating an `EditForm`, you specify what model instance to bind to using the `Model` parameter.</span></span> <span data-ttu-id="969b5-118">La convalida viene in genere eseguita utilizzando le annotazioni dei dati ed è estendibile.</span><span class="sxs-lookup"><span data-stu-id="969b5-118">Validation is typically done using data annotations, and it's extensible.</span></span> <span data-ttu-id="969b5-119">Per abilitare la convalida basata sull'annotazione dei dati, aggiungere il `DataAnnotationsValidator` componente come elemento figlio di `EditForm` .</span><span class="sxs-lookup"><span data-stu-id="969b5-119">To enable data annotation-based validation, add the `DataAnnotationsValidator` component as a child of the `EditForm`.</span></span> <span data-ttu-id="969b5-120">Il `EditForm` componente fornisce un pratico evento per la gestione degli `OnValidSubmit` invii validi () e non validi ( `OnInvalidSubmit` ).</span><span class="sxs-lookup"><span data-stu-id="969b5-120">The `EditForm` component provides a convenient event for handling valid (`OnValidSubmit`) and invalid (`OnInvalidSubmit`) submissions.</span></span> <span data-ttu-id="969b5-121">È inoltre disponibile un evento più generico `OnSubmit` che consente di attivare e gestire autonomamente la convalida.</span><span class="sxs-lookup"><span data-stu-id="969b5-121">There's also a more generic `OnSubmit` event that lets you trigger and handle the validation yourself.</span></span>

<span data-ttu-id="969b5-122">Per visualizzare un riepilogo degli errori di convalida, utilizzare il `ValidationSummary` componente.</span><span class="sxs-lookup"><span data-stu-id="969b5-122">To display a validation error summary, use the `ValidationSummary` component.</span></span> <span data-ttu-id="969b5-123">Per visualizzare i messaggi di convalida per un campo di input specifico, utilizzare il `ValidationMessage` componente, specificando un'espressione lambda per il `For` parametro che punta al membro del modello appropriato.</span><span class="sxs-lookup"><span data-stu-id="969b5-123">To display validation messages for a specific input field, use the `ValidationMessage` component, specifying a lambda expression for the `For` parameter that points to the appropriate model member.</span></span>

<span data-ttu-id="969b5-124">Il tipo di modello seguente definisce diverse regole di convalida usando le annotazioni dei dati:</span><span class="sxs-lookup"><span data-stu-id="969b5-124">The following model type defines several validation rules using data annotations:</span></span>

```csharp
using System;
using System.ComponentModel.DataAnnotations;

public class Starship
{
    [Required]
    [StringLength(16,
        ErrorMessage = "Identifier too long (16 character limit).")]
    public string Identifier { get; set; }

    public string Description { get; set; }

    [Required]
    public string Classification { get; set; }

    [Range(1, 100000,
        ErrorMessage = "Accommodation invalid (1-100000).")]
    public int MaximumAccommodation { get; set; }

    [Required]
    [Range(typeof(bool), "true", "true",
        ErrorMessage = "This form disallows unapproved ships.")]
    public bool IsValidatedDesign { get; set; }

    [Required]
    public DateTime ProductionDate { get; set; }
}
```

<span data-ttu-id="969b5-125">Nel componente seguente viene illustrata la compilazione di un form in in Blazor base al `Starship` tipo di modello:</span><span class="sxs-lookup"><span data-stu-id="969b5-125">The following component demonstrates building a form in Blazor based on the `Starship` model type:</span></span>

```razor
<h1>New Ship Entry Form</h1>

<EditForm Model="@starship" OnValidSubmit="@HandleValidSubmit">
    <DataAnnotationsValidator />
    <ValidationSummary />

    <p>
        <label for="identifier">Identifier: </label>
        <InputText id="identifier" @bind-Value="starship.Identifier" />
        <ValidationMessage For="() => starship.Identifier" />
    </p>
    <p>
        <label for="description">Description (optional): </label>
        <InputTextArea id="description" @bind-Value="starship.Description" />
    </p>
    <p>
        <label for="classification">Primary Classification: </label>
        <InputSelect id="classification" @bind-Value="starship.Classification">
            <option value="">Select classification ...</option>
            <option value="Exploration">Exploration</option>
            <option value="Diplomacy">Diplomacy</option>
            <option value="Defense">Defense</option>
        </InputSelect>
        <ValidationMessage For="() => starship.Classification" />
    </p>
    <p>
        <label for="accommodation">Maximum Accommodation: </label>
        <InputNumber id="accommodation" @bind-Value="starship.MaximumAccommodation" />
        <ValidationMessage For="() => starship.MaximumAccommodation" />
    </p>
    <p>
        <label for="valid">Engineering Approval: </label>
        <InputCheckbox id="valid" @bind-Value="starship.IsValidatedDesign" />
        <ValidationMessage For="() => starship.IsValidatedDesign" />
    </p>
    <p>
        <label for="productionDate">Production Date: </label>
        <InputDate id="productionDate" @bind-Value="starship.ProductionDate" />
        <ValidationMessage For="() => starship.ProductionDate" />
    </p>

    <button type="submit">Submit</button>
</EditForm>

@code {
    private Starship starship = new Starship();

    private void HandleValidSubmit()
    {
        // Save the data
    }
}
```

<span data-ttu-id="969b5-126">Dopo l'invio del modulo, i dati associati al modello non sono stati salvati in alcun archivio dati, ad esempio un database.</span><span class="sxs-lookup"><span data-stu-id="969b5-126">After the form submission, the model-bound data hasn't been saved to any data store, like a database.</span></span> <span data-ttu-id="969b5-127">In un' Blazor WebAssembly applicazione i dati devono essere inviati al server.</span><span class="sxs-lookup"><span data-stu-id="969b5-127">In a Blazor WebAssembly app, the data must be sent to the server.</span></span> <span data-ttu-id="969b5-128">Ad esempio, usando una richiesta HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="969b5-128">For example, using an HTTP POST request.</span></span> <span data-ttu-id="969b5-129">In un' Blazor app Server, i dati sono già presenti sul server, ma devono essere salvati in maniera permanente.</span><span class="sxs-lookup"><span data-stu-id="969b5-129">In a Blazor Server app, the data is already on the server, but it must be persisted.</span></span> <span data-ttu-id="969b5-130">La gestione dell'accesso ai dati nelle Blazor app è l'oggetto della sezione relativa alla gestione [dei dati](data.md) .</span><span class="sxs-lookup"><span data-stu-id="969b5-130">Handling data access in Blazor apps is the subject of the [Dealing with data](data.md) section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="969b5-131">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="969b5-131">Additional resources</span></span>

<span data-ttu-id="969b5-132">Per ulteriori informazioni sui [moduli e la convalida](/aspnet/core/blazor/forms-validation) nelle Blazor app, vedere la Blazor documentazione di.</span><span class="sxs-lookup"><span data-stu-id="969b5-132">For more information on [forms and validation](/aspnet/core/blazor/forms-validation) in Blazor apps, see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="969b5-133">[Precedente](state-management.md) 
> [Avanti](data.md)</span><span class="sxs-lookup"><span data-stu-id="969b5-133">[Previous](state-management.md)
[Next](data.md)</span></span>
