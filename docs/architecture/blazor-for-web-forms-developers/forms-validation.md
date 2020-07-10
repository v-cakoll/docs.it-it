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
# <a name="forms-and-validation"></a>Moduli e convalida

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Il framework Web Form ASP.NET include un set di controlli server di convalida che gestiscono la convalida dell'input utente immesso in un modulo ( `RequiredFieldValidator` ,, `CompareValidator` `RangeValidator` e così via). Il framework Web Form ASP.NET supporta anche l'associazione di modelli e la convalida del modello in base alle annotazioni dei dati ( `[Required]` ,, `[StringLength]` `[Range]` e così via). La logica di convalida può essere applicata sia nel server che nel client usando la convalida basata su JavaScript non intrusiva. Il `ValidationSummary` controllo server viene utilizzato per visualizzare un riepilogo degli errori di convalida per l'utente.

Blazorsupporta la condivisione della logica di convalida tra il client e il server. ASP.NET fornisce implementazioni JavaScript predefinite di molte convalide server comuni. In molti casi, lo sviluppatore deve ancora scrivere codice JavaScript per implementare completamente la logica di convalida specifica dell'app. Gli stessi tipi di modello, le annotazioni dei dati e la logica di convalida possono essere utilizzati sia sul server che sul client.

Blazorfornisce un set di componenti di input. I componenti di input gestiscono i dati dei campi di associazione a un modello e convalidano l'input dell'utente quando viene inviato il modulo.

|Componente di input|Elemento HTML sottoposto a rendering    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

Il `EditForm` componente esegue il wrapping di questi componenti di input e orchestra il processo di convalida tramite un `EditContext` . Quando si crea un oggetto `EditForm` , è necessario specificare l'istanza del modello da associare a utilizzando il `Model` parametro. La convalida viene in genere eseguita utilizzando le annotazioni dei dati ed è estendibile. Per abilitare la convalida basata sull'annotazione dei dati, aggiungere il `DataAnnotationsValidator` componente come elemento figlio di `EditForm` . Il `EditForm` componente fornisce un pratico evento per la gestione degli `OnValidSubmit` invii validi () e non validi ( `OnInvalidSubmit` ). È inoltre disponibile un evento più generico `OnSubmit` che consente di attivare e gestire autonomamente la convalida.

Per visualizzare un riepilogo degli errori di convalida, utilizzare il `ValidationSummary` componente. Per visualizzare i messaggi di convalida per un campo di input specifico, utilizzare il `ValidationMessage` componente, specificando un'espressione lambda per il `For` parametro che punta al membro del modello appropriato.

Il tipo di modello seguente definisce diverse regole di convalida usando le annotazioni dei dati:

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

Nel componente seguente viene illustrata la compilazione di un form in in Blazor base al `Starship` tipo di modello:

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

Dopo l'invio del modulo, i dati associati al modello non sono stati salvati in alcun archivio dati, ad esempio un database. In un' Blazor WebAssembly applicazione i dati devono essere inviati al server. Ad esempio, usando una richiesta HTTP POST. In un' Blazor app Server, i dati sono già presenti sul server, ma devono essere salvati in maniera permanente. La gestione dell'accesso ai dati nelle Blazor app è l'oggetto della sezione relativa alla gestione [dei dati](data.md) .

## <a name="additional-resources"></a>Risorse aggiuntive

Per ulteriori informazioni sui [moduli e la convalida](/aspnet/core/blazor/forms-validation) nelle Blazor app, vedere la Blazor documentazione di.

>[!div class="step-by-step"]
>[Precedente](state-management.md) 
> [Avanti](data.md)
