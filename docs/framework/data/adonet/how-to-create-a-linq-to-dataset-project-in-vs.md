---
title: Creare un progetto LINQ to DataSet In Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 22763d3b9581d09d7bdda0c09480f8d36bb8e2ec
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297016"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="7a948-102">Procedura: creare un progetto LINQ to DataSet In Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7a948-102">How to: Create a LINQ to DataSet project In Visual Studio</span></span>

<span data-ttu-id="7a948-103">I diversi tipi di progetti LINQ richiedono alcuni riferimenti ad assembly e spazi dei nomi importati (Visual Basic) o [usando](../../../csharp/language-reference/keywords/using-directive.md) direttive (c#).</span><span class="sxs-lookup"><span data-stu-id="7a948-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="7a948-104">Il requisito minimo per LINQ è un riferimento a *DLL* e una `using` direttiva <xref:System.Linq>.</span><span class="sxs-lookup"><span data-stu-id="7a948-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="7a948-105">Questi requisiti vengono forniti per impostazione predefinita se si crea un nuovo progetto app di console c# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="7a948-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017.</span></span> <span data-ttu-id="7a948-106">Se si aggiorna un progetto da una versione precedente di Visual Studio, è necessario specificare manualmente questi riferimenti correlati a LINQ.</span><span class="sxs-lookup"><span data-stu-id="7a948-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="7a948-107">LINQ to DataSet richiede due ulteriori riferimenti al *System* e *DataSetExtensions. dll*.</span><span class="sxs-lookup"><span data-stu-id="7a948-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="7a948-108">Se si sta creando da un prompt dei comandi, è necessario fare manualmente riferimento le DLL correlate a LINQ nello *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span><span class="sxs-lookup"><span data-stu-id="7a948-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="7a948-109">Per abilitare la funzionalità LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="7a948-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="7a948-110">Seguire questi passaggi per abilitare LINQ alle funzionalità di set di dati in un progetto esistente.</span><span class="sxs-lookup"><span data-stu-id="7a948-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="7a948-111">Aggiungere riferimenti agli **System. core**, **System. Data**, e **System.Data.DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="7a948-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="7a948-112">Nelle **Esplora soluzioni**, fare clic sul **riferimenti** nodo e selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="7a948-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="7a948-113">Nel **gestione riferimenti** finestra di dialogo **System. core**, **System. Data**, e **System.Data.DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="7a948-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="7a948-114">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a948-114">Select **OK**.</span></span>

1. <span data-ttu-id="7a948-115">Aggiungere [usando](../../../csharp/language-reference/keywords/using-directive.md) direttive (oppure [istruzioni Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) per **System. Data** e **LINQ**.</span><span class="sxs-lookup"><span data-stu-id="7a948-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="7a948-116">Facoltativamente, aggiungere un `using` direttiva (o `Imports` istruzione) per **spazio** oppure **SqlClient**, a seconda della modalità di connessione al database.</span><span class="sxs-lookup"><span data-stu-id="7a948-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a948-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a948-117">See also</span></span>

- [<span data-ttu-id="7a948-118">Introduzione a LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="7a948-118">Get started with LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
