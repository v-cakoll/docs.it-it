---
title: 'Procedura: leggere le impostazioni in fase di esecuzione con C#'
description: Informazioni su come leggere le impostazioni con ambito di applicazione e con ambito di utente in fase di esecuzione con C# tramite l'oggetto Properties.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d784544e018bb693c501e35ea36fcae1946ef5eb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903352"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Procedura: leggere le impostazioni in fase di esecuzione con C\#

È possibile leggere le impostazioni con ambito di applicazione e con ambito di utente in fase di esecuzione tramite l'oggetto Proprietà. L'oggetto Properties espone tutte le impostazioni predefinite per il progetto tramite il membro Properties. Settings. default nello spazio dei nomi predefinito del progetto in cui sono definiti.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>Per leggere le impostazioni in fase di esecuzione con C\#
  
Accedere all'impostazione appropriata tramite il membro Properties.Settings.Default. Nell'esempio seguente viene illustrato come assegnare l'impostazione `myColor` a una proprietà BackColor. È necessario avere creato in precedenza un file di impostazioni che contenga un'impostazione denominata `myColor` di tipo `System.Drawing.Color`. Per informazioni sulla creazione di un file di impostazioni, vedere [procedura: creare una nuova impostazione in fase di progettazione](how-to-create-a-new-setting-at-design-time.md).  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Procedura: scrivere le impostazioni utente in fase di esecuzione con C#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Panoramica delle impostazioni dell'applicazione](application-settings-overview.md)
