---
title: 'Procedura: Creare una nuova impostazione in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: 35a7cd8cc1daaf76a25977751ddc9ec0709e5947
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037898"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a>Procedura: Crea una nuova impostazione in fase di progettazione

È possibile creare una nuova impostazione in fase di progettazione usando la finestra di progettazione delle impostazioni in Visual Studio. Progettazione impostazioni è un'interfaccia di tipo Grid che consente di creare nuove impostazioni e specificare le proprietà per tali impostazioni. Per le nuove impostazioni, è necessario specificare il nome, il valore, il tipo e l'ambito. Una volta creata, l'impostazione è accessibile nel codice.

## <a name="create-a-new-setting-at-design-time-in-c"></a>Creare una nuova impostazione in fase di progettazione in C\#

1. Aprire Visual Studio.

2. In **Esplora soluzioni**espandere il nodo **Proprietà** del progetto.

3. Fare doppio clic sul file. Settings in cui si desidera aggiungere una nuova impostazione. Il nome predefinito di questo file è Settings. Settings.

4. Nella finestra di progettazione delle impostazioni impostare il **nome**, il **valore**, il **tipo**e l' **ambito** per l'impostazione. Ogni riga rappresenta una singola impostazione.

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a>Crea una nuova impostazione in fase di progettazione in Visual Basic

1. Aprire Visual Studio.

2. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo del progetto e scegliere **Proprietà**.

3. Nella pagina **Proprietà** selezionare la scheda **Impostazioni** .

4. Nella finestra di progettazione delle impostazioni impostare il **nome**, il **valore**, il **tipo**e l' **ambito** per l'impostazione. Ogni riga rappresenta una singola impostazione.

## <a name="see-also"></a>Vedere anche

- [Uso delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
- [Procedura: Modificare il valore di un'impostazione esistente in fase di progettazione](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
