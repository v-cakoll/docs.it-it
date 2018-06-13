---
title: 'Procedura: leggere le impostazioni in fase di esecuzione con C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8259e2f429718793c01868855651d1000620fae5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521014"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Procedura: leggere le impostazioni in fase di esecuzione con C# #
È possibile leggere le impostazioni con ambito di applicazione e con ambito di utente in fase di esecuzione tramite l'oggetto Proprietà. L'oggetto Proprietà espone tutte le impostazioni predefinite per il progetto tramite il membro Properties.Settings.Default.  
  
### <a name="to-read-settings-at-run-time-with-c"></a>Per leggere le impostazioni in fase di esecuzione con C#  
  
-   Accedere all'impostazione appropriata tramite il membro Properties.Settings.Default. Nell'esempio seguente viene illustrato come assegnare l'impostazione `myColor` a una proprietà BackColor. È necessario avere creato in precedenza un file di impostazioni che contenga un'impostazione denominata `myColor` di tipo `System.Drawing.Color`. Per informazioni sulla creazione di un file di impostazioni, vedere [procedura: creare una nuova impostazione in fase di progettazione](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Uso delle impostazioni applicazione e delle impostazioni utente](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Procedura: Scrivere le impostazioni utente in fase di esecuzione con C#](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
 [Cenni preliminari sulle impostazioni delle applicazioni](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
