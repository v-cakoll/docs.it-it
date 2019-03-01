---
title: 'Procedura: Scrivere le impostazioni utente in fase di esecuzione conC#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 264fa9706f9255d7324cad6d02c36cc424e28995
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981595"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>Procedura: Scrivere le impostazioni utente in fase di esecuzione con C\#

Le impostazioni con ambito di applicazione sono di sola lettura e possono essere modificate solo in fase di progettazione o modificando il file .config tra sessioni dell'applicazione. Le impostazioni con ambito di utente possono invece essere scritte in fase di esecuzione usando la stessa procedura adottata per modificare il valore di una proprietà. Il nuovo valore viene mantenuto per la durata della sessione dell'applicazione. È possibile mantenere le modifiche alle impostazioni tra le sessioni dell'applicazione chiamando il metodo Save.  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>Procedura: Scrivere e mantenere le impostazioni utente in fase di esecuzione con C\#
  
1. Accedere all'impostazione e assegnarle un nuovo valore come mostrato nell'esempio seguente:  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. Se si vogliono mantenere le modifiche alle impostazioni tra sessioni dell'applicazione, chiamare il metodo Save, come mostrato nell'esempio seguente:  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
Le impostazioni utente vengono salvate in un file all'interno di una sottocartella della cartella dati applicazioni nascosta locale dell'utente.  
  
## <a name="see-also"></a>Vedere anche

- [Uso delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Procedura: Leggere le impostazioni in fase di esecuzione conC#](how-to-read-settings-at-run-time-with-csharp.md)
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
