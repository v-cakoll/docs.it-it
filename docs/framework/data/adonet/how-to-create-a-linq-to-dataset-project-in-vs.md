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
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Procedura: creare un progetto LINQ to DataSet In Visual Studio

I diversi tipi di progetti LINQ richiedono alcuni riferimenti ad assembly e spazi dei nomi importati (Visual Basic) o [usando](../../../csharp/language-reference/keywords/using-directive.md) direttive (c#). Il requisito minimo per LINQ è un riferimento a *DLL* e una `using` direttiva <xref:System.Linq>.

Questi requisiti vengono forniti per impostazione predefinita se si crea un nuovo progetto app di console c# in Visual Studio 2017. Se si aggiorna un progetto da una versione precedente di Visual Studio, è necessario specificare manualmente questi riferimenti correlati a LINQ.

LINQ to DataSet richiede due ulteriori riferimenti al *System* e *DataSetExtensions. dll*.

> [!NOTE]
> Se si sta creando da un prompt dei comandi, è necessario fare manualmente riferimento le DLL correlate a LINQ nello *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.

## <a name="to-enable-linq-to-dataset-functionality"></a>Per abilitare la funzionalità LINQ to DataSet

Seguire questi passaggi per abilitare LINQ alle funzionalità di set di dati in un progetto esistente.

1. Aggiungere riferimenti agli **System. core**, **System. Data**, e **System.Data.DataSetExtensions**.

   Nelle **Esplora soluzioni**, fare clic sul **riferimenti** nodo e selezionare **Aggiungi riferimento**. Nel **gestione riferimenti** finestra di dialogo **System. core**, **System. Data**, e **System.Data.DataSetExtensions**. Scegliere **OK**.

1. Aggiungere [usando](../../../csharp/language-reference/keywords/using-directive.md) direttive (oppure [istruzioni Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) per **System. Data** e **LINQ**.

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. Facoltativamente, aggiungere un `using` direttiva (o `Imports` istruzione) per **spazio** oppure **SqlClient**, a seconda della modalità di connessione al database.

## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ to DataSet](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
