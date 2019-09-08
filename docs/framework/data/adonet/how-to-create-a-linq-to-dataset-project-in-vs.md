---
title: Creare un progetto di LINQ to DataSet in Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 8b905c65575c3c567459d843b2a5d1606bc63228
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783771"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Procedura: Creare un progetto di LINQ to DataSet in Visual Studio

Per i diversi tipi di progetti LINQ sono necessari determinati riferimenti ad assembly e spazi dei nomi importati (Visual BasicC#) o direttive [using](../../../csharp/language-reference/keywords/using-directive.md) (). Il requisito minimo per LINQ è un riferimento a *System. Core. dll* e una `using` direttiva per <xref:System.Linq>.

Questi requisiti vengono forniti per impostazione predefinita se si crea un C# nuovo progetto di app console in Visual Studio 2017. Se si sta aggiornando un progetto da una versione precedente di Visual Studio, potrebbe essere necessario fornire manualmente questi riferimenti correlati a LINQ.

LINQ to DataSet richiede due riferimenti aggiuntivi a *System. Data. dll* e *System. Data. datasetextensions. dll*.

> [!NOTE]
> Se si esegue la compilazione da un prompt dei comandi, è necessario fare manualmente riferimento alle DLL correlate a LINQ in *%programmi%\Reference Assemblies\Microsoft\Framework\v3.5*.

## <a name="to-enable-linq-to-dataset-functionality"></a>Per abilitare la funzionalità LINQ to DataSet

Seguire questa procedura per abilitare la funzionalità di LINQ to DataSet in un progetto esistente.

1. Aggiungere riferimenti a **System. Core**, **System. Data**e **System. Data. datasetextensions**.

   In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo **riferimenti** e selezionare **Aggiungi riferimento**. Nella finestra di dialogo **Gestione riferimenti** selezionare **System. Core**, **System. Data**e **System. Data. datasetextensions**. Scegliere **OK**.

1. Aggiungere direttive [using](../../../csharp/language-reference/keywords/using-directive.md) (o [istruzioni Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) per **System. Data** e **System. Linq**.

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. Facoltativamente, aggiungere una `using` direttiva (o `Imports` un'istruzione) per **System. Data. Common** o **System. Data. SqlClient**, a seconda della modalità di connessione al database.

## <a name="see-also"></a>Vedere anche

- [Inizia a usare LINQ to DataSet](getting-started-linq-to-dataset.md)
