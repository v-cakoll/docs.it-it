---
title: 'Procedura: Leggere le impostazioni in fase di esecuzione con C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 6a40718d57fad4041eeea2fded03b7256abbe8d1
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710218"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Procedura: Leggere le impostazioni in fase di esecuzione con C\#

È possibile leggere le impostazioni con ambito di applicazione e con ambito di utente in fase di esecuzione tramite l'oggetto Proprietà. L'oggetto Properties espone tutte le impostazioni predefinite per il progetto tramite il membro Properties. Settings. default nello spazio dei nomi predefinito del progetto in cui sono definiti.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>Per leggere le impostazioni in fase di esecuzione con C\#
  
Accedere all'impostazione appropriata tramite il membro Properties.Settings.Default. Nell'esempio seguente viene illustrato come assegnare l'impostazione `myColor` a una proprietà BackColor. È necessario avere creato in precedenza un file di impostazioni che contenga un'impostazione denominata `myColor` di tipo `System.Drawing.Color`. Per informazioni sulla creazione di un file di impostazioni [, vedere Procedura: Crea una nuova impostazione in fase](how-to-create-a-new-setting-at-design-time.md)di progettazione.  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>Vedere anche

- [Uso delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Procedura: Scrivere le impostazioni utente in fase di esecuzione conC#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
