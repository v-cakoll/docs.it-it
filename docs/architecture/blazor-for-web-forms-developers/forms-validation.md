---
title: Moduli e convalida
description: Informazioni su come compilare moduli con la convalida lato client in blazer.
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: c30db5e06d36a6d15301835fe782b21058a80592
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088081"
---
# <a name="forms-and-validation"></a>Moduli e convalida

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Il framework Web Form ASP.NET include un set di controlli server di convalida che gestiscono la convalida dell'input utente immesso in un modulo (`RequiredFieldValidator`, `CompareValidator`, `RangeValidator`e così via). Il framework Web Form ASP.NET supporta anche l'associazione di modelli e la convalida del modello in base alle annotazioni dei dati (`[Required]`, `[StringLength]`, `[Range]`e così via). La logica di convalida può essere applicata sia nel server che nel client usando la convalida basata su JavaScript non intrusiva. Il controllo `ValidationSummary` server viene utilizzato per visualizzare un riepilogo degli errori di convalida per l'utente.

Blazer supporta la condivisione della logica di convalida tra il client e il server. ASP.NET fornisce implementazioni JavaScript predefinite di molte convalide server comuni. In molti casi, lo sviluppatore deve ancora scrivere codice JavaScript per implementare completamente la logica di convalida specifica dell'app. Gli stessi tipi di modello, le annotazioni dei dati e la logica di convalida possono essere utilizzati sia sul server che sul client.

Blazer fornisce un set di componenti di input. I componenti di input gestiscono i dati dei campi di associazione a un modello e convalidano l'input dell'utente quando viene inviato il modulo.

|Componente di input|Elemento HTML sottoposto a rendering    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

Il componente `EditForm` esegue il wrapping di questi componenti di input e orchestra il processo di convalida tramite una `EditContext`. Quando si crea una `EditForm`, è necessario specificare l'istanza del modello da associare utilizzando il parametro `Model`. La convalida viene in genere eseguita utilizzando le annotazioni dei dati ed è estendibile. Per abilitare la convalida basata sull'annotazione dei dati, aggiungere il componente `DataAnnotationsValidator` come figlio del `EditForm`. Il componente `EditForm` fornisce un pratico evento per la gestione degli invii validi (`OnValidSubmit`) e non validi (`OnInvalidSubmit`). Esiste anche un evento `OnSubmit` più generico che consente di attivare e gestire la convalida autonomamente.

Per visualizzare un riepilogo degli errori di convalida, utilizzare il componente `ValidationSummary`. Per visualizzare i messaggi di convalida per un campo di input specifico, usare il componente `ValidationMessage`, specificando un'espressione lambda per il parametro `For` che punta al membro del modello appropriato.

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

Il componente seguente illustra la creazione di un modulo in blazer in base al tipo di modello di `Starship`:

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

Dopo l'invio del modulo, i dati associati al modello non sono stati salvati in alcun archivio dati, ad esempio un database. In un'app webassembly Blazer i dati devono essere inviati al server. Ad esempio, usando una richiesta HTTP POST. In un'app Server Blazer i dati sono già presenti nel server, ma devono essere salvati in maniera permanente. La gestione dell'accesso ai dati nelle app blazer è l'oggetto della sezione relativa alla gestione dei [dati](data.md) .

## <a name="additional-resources"></a>Risorse aggiuntive

Per ulteriori informazioni sui [moduli e la convalida](/aspnet/core/blazor/forms-validation) nelle app blazer, vedere la documentazione di Blazer.

>[!div class="step-by-step"]
>[Precedente](state-management.md)
>[Successivo](data.md)
