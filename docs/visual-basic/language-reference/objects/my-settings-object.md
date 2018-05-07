---
title: Oggetto My.Settings
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 54176ae6706311b17227c7dc21a5060c9b369753
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="mysettings-object"></a>Oggetto My.Settings
Fornisce proprietà e metodi per accedere alle impostazioni dell'applicazione.  
  
## <a name="remarks"></a>Note  
 Il `My.Settings` oggetto fornisce accesso alle impostazioni dell'applicazione e consente di archiviare e recuperare le impostazioni delle proprietà e altre informazioni per l'applicazione in modo dinamico. Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Proprietà  
 Le proprietà dell'oggetto `My.Settings` offrono accesso alle impostazioni dell'applicazione. Per aggiungere o rimuovere le impostazioni, utilizzare il **Progettazione impostazioni**.  
  
 Ogni impostazione abbia un **nome**, **tipo**, **ambito**, e **valore**, e queste impostazioni determinano come la proprietà di accesso a ogni impostazione è presente il `My.Settings` oggetto:  
  
-   **Nome** determina il nome della proprietà.  
  
-   **Tipo** determina il tipo della proprietà.  
  
-   **Ambito** indica se la proprietà è di sola lettura. Se il valore è **applicazione**, la proprietà è di sola lettura; se il valore è **utente**, la proprietà è di sola lettura.  
  
-   **Valore** è il valore predefinito della proprietà.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|---|---|  
|`Reload`|Consente di ricaricare le impostazioni utente da ultimi valori salvati.|  
|`Save`|Salva le impostazioni utente correnti.|  
  
 Il `My.Settings` oggetto fornisce inoltre le proprietà avanzate ed ereditati dalla <xref:System.Configuration.ApplicationSettingsBase> classe.  
  
## <a name="tasks"></a>Attività  
 Nella tabella seguente sono elencati esempi di attività che coinvolgono la `My.Settings` oggetto.  
  
|A|Vedere|  
|---|---|  
|Leggere un'impostazione dell'applicazione|[Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Modificare un'impostazione utente|[Procedura: Modificare le impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Mantenere le impostazioni utente|[Procedura: Mantenere le impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Creare una griglia delle proprietà per le impostazioni utente|[Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene mostrato il valore dell'impostazione `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione `Nickname` di tipo `String`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [Procedura: Modificare le impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [Procedura: Mantenere le impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
