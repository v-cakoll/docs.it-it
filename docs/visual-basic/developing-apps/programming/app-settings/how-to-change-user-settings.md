---
title: "Procedura: Modificare le impostazioni dell'utente"
ms.date: 07/20/2015
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
ms.openlocfilehash: c9b89459f9b443c3a447edce90fee3437bbf1b6a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410179"
---
# <a name="how-to-change-user-settings-in-visual-basic"></a>Procedura: modificare le impostazioni dell'utente in Visual Basic

È possibile modificare un'impostazione utente assegnando un nuovo valore alla proprietà dell'impostazione nell'oggetto `My.Settings`.  
  
 L'oggetto `My.Settings` espone ogni impostazione come una proprietà. Il nome della proprietà corrisponde allo stesso nome dell'impostazione e il tipo di proprietà al tipo di impostazione. L'**ambito** dell'impostazione determina se la proprietà è di sola lettura. La proprietà di un'impostazione dell'ambito dell'**applicazione** è di sola lettura, mentre la proprietà di un'impostazione dell'ambito dell'**utente**-è di lettura e scrittura. Per altre informazioni, vedere [Oggetto My.Settings](../../../language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
> Sebbene sia possibile modificare e salvare i valori delle impostazioni dell'ambito dell'utente in fase di esecuzione, le impostazioni dell'ambito dell'applicazione sono di sola lettura e non possono essere modificate a livello di codice. È possibile modificare le impostazioni dell'ambito dell'applicazione quando si crea l'applicazione tramite **Creazione progetti** o modificando il file di configurazione dell'applicazione. Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Esempio  

 Questo esempio modifica il valore dell'impostazione utente `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#7)]  
  
 Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione utente `Nickname` di tipo `String`.  
  
 Alla chiusura dell'applicazione vengono salvate le impostazioni utente. Per salvare immediatamente le impostazioni, chiamare il metodo `My.Settings.Save`. Per altre informazioni, vedere [Procedura: Mantenere le impostazioni dell'utente in Visual Basic](how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>Vedere anche

- [Oggetto My.Settings](../../../language-reference/objects/my-settings-object.md)
- [Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](how-to-read-application-settings.md)
- [Procedura: Mantenere le impostazioni dell'utente in Visual Basic](how-to-persist-user-settings.md)
- [Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](how-to-create-property-grids-for-user-settings.md)
- [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
