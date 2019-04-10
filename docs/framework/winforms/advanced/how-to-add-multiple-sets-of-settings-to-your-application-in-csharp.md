---
title: "Procedura: Aggiungere più set di impostazioni all'applicazione in C#"
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 9a4913f635204aac2214d97225c7b8147c6fe9ab
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59326606"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Procedura: Aggiungere più set di impostazioni dell'applicazione in C\#
In alcuni casi, è consigliabile avere più set di impostazioni in un'applicazione. Ad esempio, se si sviluppa un'applicazione posto di un determinato gruppo di impostazioni di cambiare frequentemente, è possibile raggrupparle tutto in un singolo file in modo che il file può essere sostituito a livello globale, lasciando inalterate le altre impostazioni. Visual Studio consente di aggiungere più set di impostazioni al progetto. Altri set di impostazioni sono accessibili tramite l'oggetto Properties. Settings.  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>Per aggiungere un ulteriore Set di impostazioni all'applicazione  
  
1. Dal menu **Progetto**, scegliere **Aggiungi nuovo elemento**. Viene aperta la finestra di dialogo **Aggiungi nuovo elemento**.  
  
2. Nel **Aggiungi nuovo elemento** finestra di dialogo **File di impostazioni**, digitare un nome per il file e fare clic su **Add** per aggiungere un nuovo file di impostazioni per la soluzione.  
  
3. Nelle **Esplora soluzioni**, trascinare il nuovo file di impostazioni nel **proprietà** cartella. In questo modo le nuove impostazioni saranno disponibili nel codice.  
  
4. Aggiungere e usare le impostazioni in questo file come si farebbe con qualsiasi altro file di impostazioni. È possibile accedere a questo gruppo di impostazioni tramite l'oggetto Properties. Settings.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
