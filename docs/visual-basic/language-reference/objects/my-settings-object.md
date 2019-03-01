---
title: Oggetto My. Settings (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 5d6d56e4a1eddcb687fe042568509ba489aa8bb3
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973470"
---
# <a name="mysettings-object"></a>Oggetto My.Settings
Fornisce proprietà e metodi per l'accesso alle impostazioni dell'applicazione.  
  
## <a name="remarks"></a>Note  
 Il `My.Settings` oggetto consente di accedere alle impostazioni dell'applicazione e consente di archiviare e recuperare le impostazioni delle proprietà e altre informazioni per l'applicazione in modo dinamico. Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Proprietà  
 Le proprietà dell'oggetto `My.Settings` offrono accesso alle impostazioni dell'applicazione. Per aggiungere o rimuovere le impostazioni, usare il **Progettazione impostazioni**.  
  
 Ciascuna impostazione dispone di un **Name**, **tipo**, **ambito**, e **valore**, e queste impostazioni determinano come la proprietà di accesso a ogni impostazione viene visualizzato nei `My.Settings` oggetto:  
  
-   **Nome** determina il nome della proprietà.  
  
-   **Tipo** determina il tipo della proprietà.  
  
-   **Ambito** indica se la proprietà è di sola lettura. Se il valore è **Application**, la proprietà è di sola lettura; se il valore è **utente**, la proprietà è di lettura / scrittura.  
  
-   **Valore** è il valore predefinito della proprietà.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|---|---|  
|`Reload`|Consente di ricaricare le impostazioni utente da ultimi valori salvati.|  
|`Save`|Salva le impostazioni utente correnti.|  
  
 Il `My.Settings` oggetto fornisce anche le proprietà avanzate e i metodi, ereditati dal <xref:System.Configuration.ApplicationSettingsBase> classe.  
  
## <a name="tasks"></a>Attività  
 La tabella seguente elenca alcuni esempi di attività che implicano il `My.Settings` oggetto.  
  
|A|Vedere|  
|---|---|  
|Leggere un'impostazione dell'applicazione|[Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Modificare un'impostazione utente|[Procedura: Modificare le impostazioni dell'utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Mantenere le impostazioni utente|[Procedura: Mantenere le impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Creare una griglia delle proprietà per impostazioni utente|[Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene mostrato il valore dell'impostazione `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione `Nickname` di tipo `String`.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Configuration.ApplicationSettingsBase>
- [Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Procedura: Modificare le impostazioni dell'utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Procedura: Mantenere le impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
