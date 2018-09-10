---
title: 'Procedura: creare una chiave nel Registro di sistema (Visual C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: 383d47413078359d7491bf5f7f61dc5e70d842a7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526738"
---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a>Procedura: creare una chiave nel Registro di sistema (Visual C#)
Nell'esempio riportato di seguito viene aggiunta la coppia di valori "Name" e "Isabella" alla chiave "Names"del Registro di sistema dell'utente corrente.  
  
## <a name="example"></a>Esempio  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Copiare il codice e incollarlo nel metodo `Main` di un'applicazione console.  
  
-   Sostituire il parametro `Names` con il nome di una chiave esistente direttamente nel nodo HKEY_CURRENT_USER del Registro di sistema.  
  
-   Sostituire il parametro `Name` con il nome di un valore esistente direttamente nel nodo Names.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Esaminare la struttura del Registro di sistema per individuare un percorso adatto per la chiave. Può essere necessario, ad esempio, aprire la chiave Software dell'utente corrente e creare una chiave con il nome della propria società, quindi aggiungere i valori del Registro di sistema alla chiave della società stessa.  
  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Il nome della chiave è null.  
  
-   L'utente non dispone di autorizzazioni per la creazione di chiavi del Registro di sistema.  
  
-   Il nome della chiave supera il limite di 255 caratteri.  
  
-   La chiave è chiusa.  
  
-   La chiave del Registro di sistema è di sola lettura.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 È più sicuro scrivere i dati nella cartella dell'utente, ovvero `Microsoft.Win32.Registry.CurrentUser`, anziché nel computer locale, ovvero `Microsoft.Win32.Registry.LocalMachine`.  
  
 Quando si crea un valore del Registro di sistema, è necessario decidere come procedere nel caso in cui tale valore esista già. È possibile che un altro processo, forse dannoso, abbia già creato il valore e possa accedervi. I dati inseriti nel valore del Registro di sistema sono disponibili per altri processi. Per evitare che ciò accada, usare il metodo `Overload:Microsoft.Win32.RegistryKey.GetValue` ProcessOnStatus. Restituisce null se la chiave non esiste.  
  
 Archiviare come testo nel Registro di sistema informazioni riservate, quali le password, può presentare dei rischi, anche se la chiave del Registro di sistema è protetta da elenchi di controllo di accesso (ACL, Access Control List).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO?displayProperty=nameWithType>  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [File system e Registro di sistema (Guida per programmatori C#)](../../../csharp/programming-guide/file-system/index.md)  
- [Read, write and delete from the registry with C#](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C) (Leggere, scrivere ed eliminare dal Registro di sistema con C#)
