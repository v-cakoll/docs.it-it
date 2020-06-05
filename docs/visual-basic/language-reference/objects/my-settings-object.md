---
title: Oggetto My.Settings
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: c905ff85c8e9729dd4d6068f0d34f729962bbb57
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372401"
---
# <a name="mysettings-object"></a>Oggetto My.Settings
Fornisce le proprietà e i metodi per l'accesso alle impostazioni dell'applicazione.  
  
## <a name="remarks"></a>Commenti  
 L' `My.Settings` oggetto fornisce l'accesso alle impostazioni dell'applicazione e consente di archiviare e recuperare dinamicamente le impostazioni delle proprietà e altre informazioni per l'applicazione. Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Proprietà  
 Le proprietà dell'oggetto `My.Settings` offrono accesso alle impostazioni dell'applicazione. Per aggiungere o rimuovere le impostazioni, utilizzare la **finestra di progettazione impostazioni**.  
  
 Ogni impostazione ha un **nome**, un **tipo**, un **ambito**e un **valore**e queste impostazioni determinano il modo in cui la proprietà per accedere a ogni impostazione viene visualizzata nell' `My.Settings` oggetto:  
  
- **Nome** determina il nome della proprietà.  
  
- Il **tipo** determina il tipo della proprietà.  
  
- **Scope** indica se la proprietà è di sola lettura. Se il valore è **Application**, la proprietà è di sola lettura. Se il valore è **User**, la proprietà è di lettura/scrittura.  
  
- **Value** è il valore predefinito della proprietà.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|---|---|  
|`Reload`|Ricarica le impostazioni utente dagli ultimi valori salvati.|  
|`Save`|Salva le impostazioni dell'utente corrente.|  
  
 L' `My.Settings` oggetto fornisce anche proprietà e metodi avanzati, ereditati dalla <xref:System.Configuration.ApplicationSettingsBase> classe.  
  
## <a name="tasks"></a>Attività  
 Nella tabella seguente sono elencati esempi di attività relative all' `My.Settings` oggetto.  
  
|A|Vedere|  
|---|---|  
|Leggi un'impostazione dell'applicazione|[Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Modificare un'impostazione utente|[Procedura: modificare le impostazioni dell'utente in Visual Basic](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Mantieni impostazioni utente|[Procedura: Mantenere le impostazioni dell'utente in Visual Basic](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Creare una griglia di proprietà per le impostazioni utente|[Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene mostrato il valore dell'impostazione `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione `Nickname` di tipo `String`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.ApplicationSettingsBase>
- [Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Procedura: modificare le impostazioni dell'utente in Visual Basic](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Procedura: Mantenere le impostazioni dell'utente in Visual Basic](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
