---
title: "Procedura: Modificare il valore di un'impostazione tra le sessioni dell'applicazione"
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: c1626cea581e5c180665d0ce805dea3e67f27a05
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714359"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Procedura: Modificare il valore di un'impostazione tra le sessioni dell'applicazione
In alcuni casi, si potrebbe voler modificare il valore di un'impostazione tra le sessioni dell'applicazione dopo aver compilata e distribuita l'applicazione. Ad esempio, si potrebbe voler modificare una stringa di connessione in modo che punti al percorso database corretto. Poiché gli strumenti di progettazione non sono disponibili dopo aver compilata e distribuita l'applicazione, è necessario modificare il valore dell'impostazione manualmente nel file.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>Per modificare il valore di un'impostazione tra le sessioni dell'applicazione  
  
1.  Usa Microsoft Notepad o alcuni altri editor di testo o XML, aprire il file config associato all'applicazione.  
  
2.  Individuare la voce per l'impostazione che si desidera modificare. Dovrebbe essere simile all'esempio riportato di seguito.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Digitare un nuovo valore per l'impostazione e salvare il file.  
  
## <a name="see-also"></a>Vedere anche
- [Uso delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
