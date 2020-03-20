---
title: 'Procedura: definire una stringa di connessione'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: e5b675a50f883825cce97275048447b79b64cc97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150571"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="5f2ac-102">Procedura: definire una stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="5f2ac-102">How to: Define the Connection String</span></span>

<span data-ttu-id="5f2ac-103">In questo argomento viene illustrato come definire la stringa di connessione usata per la connessione a un modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="5f2ac-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="5f2ac-104">Questo argomento è basato sul modello concettuale [AdventureWorks Sales.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5f2ac-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="5f2ac-105">Il modello Sales di AdventureWorks viene utilizzato in tutti gli argomenti correlati alle attività nella documentazione di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="5f2ac-105">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="5f2ac-106">In questo argomento si presuppone che Entity Framework sia già stato configurato e definito il modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5f2ac-106">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5f2ac-107">Per ulteriori informazioni, vedere [Procedura: definire manualmente il modello e i file](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))di mapping .</span><span class="sxs-lookup"><span data-stu-id="5f2ac-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="5f2ac-108">Le procedure descritte in questo argomento sono incluse anche in [Procedura: Configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5f2ac-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="5f2ac-109">Se si utilizza la procedura guidata Entity Data Model in un progetto di Visual Studio, viene generato automaticamente un file con estensione edmx e il progetto viene configurato per l'utilizzo di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="5f2ac-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="5f2ac-110">Per ulteriori informazioni, vedere [Procedura: utilizzare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5f2ac-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="5f2ac-111">Per definire la stringa di connessione Entity Framework</span><span class="sxs-lookup"><span data-stu-id="5f2ac-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="5f2ac-112">Aprire il file di configurazione dell'applicazione (app.config) del progetto e aggiungere la stringa di connessione seguente.</span><span class="sxs-lookup"><span data-stu-id="5f2ac-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="5f2ac-113">Se il progetto non dispone di un file di configurazione dell'applicazione, è possibile aggiungerne uno scegliendo **Aggiungi nuovo elemento** dal menu **Progetto** , selezionando la categoria **Generale** , selezionando File di **configurazione dell'applicazione**, quindi facendo clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5f2ac-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f2ac-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f2ac-114">See also</span></span>

- <span data-ttu-id="5f2ac-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5f2ac-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="5f2ac-116">[Procedura: creare un nuovo file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5f2ac-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="5f2ac-117">[Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5f2ac-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
