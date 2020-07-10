---
title: "Procedura: aggiungere più set di impostazioni all'applicazione in C#"
description: Informazioni su come aggiungere più set di impostazioni Windows Forms all'applicazione in C# usando Visual Studio.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 579374ff101758b3224bc122c46b891280ed2609
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173445"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Procedura: aggiungere più set di impostazioni all'applicazione in C\#

In alcuni casi, potrebbe essere necessario disporre di più set di impostazioni in un'applicazione. Se, ad esempio, si sta sviluppando un'applicazione in cui si prevede che un determinato gruppo di impostazioni venga modificato di frequente, è consigliabile separarli tutti in un unico file, in modo che il file possa essere sostituito in modo inverso, lasciando inalterate le altre impostazioni. Visual Studio consente di aggiungere più set di impostazioni al progetto. È possibile accedere a set aggiuntivi di impostazioni tramite l' `Properties.Settings` oggetto.

## <a name="add-an-additional-set-of-settings"></a>Aggiungere un set aggiuntivo di impostazioni

1. In Visual Studio scegliere **Aggiungi nuovo elemento**dal menu **progetto** .

   Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento** .

2. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **file di impostazioni**, immettere un nome per il file e fare clic su **Aggiungi** per aggiungere un nuovo file di impostazioni alla soluzione.

3. In **Esplora soluzioni**trascinare il nuovo file di impostazioni nella cartella **Proprietà** . In questo modo le nuove impostazioni sono disponibili nel codice.

4. Aggiungere e utilizzare le impostazioni in questo file come qualsiasi altro file di impostazioni. È possibile accedere a questo gruppo di impostazioni tramite l' `Properties.Settings` oggetto.

## <a name="see-also"></a>Vedere anche

- [Utilizzo delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Panoramica delle impostazioni dell'applicazione](application-settings-overview.md)
