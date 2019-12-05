---
title: Creare un progetto di LINQ to DataSet in Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 91032766248b11e51b90aa788b1c64c140347c25
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802019"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="33888-102">Procedura: creare un progetto di LINQ to DataSet in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="33888-102">How to: Create a LINQ to DataSet project in Visual Studio</span></span>

<span data-ttu-id="33888-103">Per i diversi tipi di progetti LINQ sono necessari determinati riferimenti ad assembly e spazi dei nomi importati (Visual BasicC#) o direttive [using](../../../csharp/language-reference/keywords/using-directive.md) ().</span><span class="sxs-lookup"><span data-stu-id="33888-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="33888-104">Il requisito minimo per LINQ è un riferimento a *System. Core. dll* e una direttiva `using` per <xref:System.Linq>.</span><span class="sxs-lookup"><span data-stu-id="33888-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="33888-105">Questi requisiti vengono forniti per impostazione predefinita se si crea un C# nuovo progetto di app console in Visual Studio 2017 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="33888-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017 or a later version.</span></span> <span data-ttu-id="33888-106">Se si sta aggiornando un progetto da una versione precedente di Visual Studio, potrebbe essere necessario fornire manualmente questi riferimenti correlati a LINQ.</span><span class="sxs-lookup"><span data-stu-id="33888-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="33888-107">LINQ to DataSet richiede due riferimenti aggiuntivi a *System. Data. dll* e *System. Data. datasetextensions. dll*.</span><span class="sxs-lookup"><span data-stu-id="33888-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="33888-108">Se si esegue la compilazione da un prompt dei comandi, è necessario fare manualmente riferimento alle DLL correlate a LINQ in *%programmi%\Reference Assemblies\Microsoft\Framework\v3.5*.</span><span class="sxs-lookup"><span data-stu-id="33888-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="33888-109">Per abilitare la funzionalità LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="33888-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="33888-110">Seguire questa procedura per abilitare la funzionalità di LINQ to DataSet in un progetto esistente.</span><span class="sxs-lookup"><span data-stu-id="33888-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="33888-111">Aggiungere riferimenti a **System. Core**, **System. Data**e **System. Data. datasetextensions**.</span><span class="sxs-lookup"><span data-stu-id="33888-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="33888-112">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo **riferimenti** e selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="33888-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="33888-113">Nella finestra di dialogo **Gestione riferimenti** selezionare **System. Core**, **System. Data**e **System. Data. datasetextensions**.</span><span class="sxs-lookup"><span data-stu-id="33888-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="33888-114">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="33888-114">Select **OK**.</span></span>

1. <span data-ttu-id="33888-115">Aggiungere direttive [using](../../../csharp/language-reference/keywords/using-directive.md) (o [istruzioni Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) per **System. Data** e **System. Linq**.</span><span class="sxs-lookup"><span data-stu-id="33888-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="33888-116">Facoltativamente, aggiungere una direttiva `using` (o un'istruzione `Imports`) per **System. Data. Common** o **System. Data. SqlClient**, a seconda della modalità di connessione al database.</span><span class="sxs-lookup"><span data-stu-id="33888-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="33888-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33888-117">See also</span></span>

- [<span data-ttu-id="33888-118">Inizia a usare LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="33888-118">Get started with LINQ to DataSet</span></span>](getting-started-linq-to-dataset.md)
