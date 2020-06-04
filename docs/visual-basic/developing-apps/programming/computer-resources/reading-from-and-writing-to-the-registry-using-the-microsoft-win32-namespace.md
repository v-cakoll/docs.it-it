---
title: Lettura e scrittura nel Registro di sistema mediante lo spazio dei nomi Microsoft.Win32
ms.date: 07/20/2015
helpviewer_keywords:
- registry [Visual Basic]
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
ms.openlocfilehash: 10431b1ad40ed320541a22fb46cc8db6dbb775b0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360072"
---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a>Lettura e scrittura nel Registro di sistema mediante lo spazio dei nomi Microsoft.Win32 (Visual Basic)

`My.Computer.Registry` dovrebbe essere in grado di soddisfare le esigenze di base della programmazione con il Registro di sistema, ma è possibile usare anche le classi <xref:Microsoft.Win32.Registry> e <xref:Microsoft.Win32.RegistryKey> dello spazio dei nomi <xref:Microsoft.Win32> di .NET Framework.  
  
## <a name="keys-in-the-registry-class"></a>Chiavi nella classe Registry  

 La classe <xref:Microsoft.Win32.Registry> include le chiavi di base del Registro di sistema che è possibile usare per accedere alle sottochiavi e ai relativi valori. Le chiavi di base sono di sola lettura. La tabella seguente elenca e descrive le sette chiavi esposte dalla classe <xref:Microsoft.Win32.Registry>.  
  
|**Codice**|**Descrizione**|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|Definisce i tipi di documento e le relative proprietà.|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|Contiene informazioni non specifiche dell'utente sulla configurazione hardware.|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|Contiene informazioni sulle preferenze dell'utente corrente, ad esempio le variabili di ambiente.|  
|<xref:Microsoft.Win32.Registry.DynData>|Contiene i dati dinamici del Registro di sistema, ad esempio quelli usati dai driver delle periferiche virtuali.|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|Contiene cinque sottochiavi (Hardware, SAM, Security, Software e System) in cui sono disponibili i dati di configurazione relativi al computer locale.|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|Contiene informazioni sulle prestazioni per i componenti software.|  
|<xref:Microsoft.Win32.Registry.Users>|Contiene informazioni sulle preferenze predefinite degli utenti.|  
  
> [!IMPORTANT]
> È più sicuro scrivere dati per l'utente corrente (<xref:Microsoft.Win32.Registry.CurrentUser>) che non per il computer locale (<xref:Microsoft.Win32.Registry.LocalMachine>). Quando la chiave che si sta creando è stata precedentemente creata da un altro processo, probabilmente dannoso, si verifica una condizione comunemente definita "squatting". Per evitare che si verifichi tale situazione, usare un metodo, ad esempio <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, che restituisce `Nothing` se la chiave non esiste già.  
  
## <a name="reading-a-value-from-the-registry"></a>Lettura di un valore dal Registro di sistema  

 Il codice seguente illustra come leggere una stringa da HKEY_CURRENT_USER.  
  
 [!code-vb[VbResourceTasks#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#20)]  
  
 Il codice seguente legge, incrementa e quindi scrive una stringa in HKEY_CURRENT_USER.  
  
 [!code-vb[VbResourceTasks#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.SystemException>
- <xref:System.ApplicationException>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [Istruzione Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md)
- [Lettura e scrittura nel Registro di sistema](reading-from-and-writing-to-the-registry.md)
- [Sicurezza e Registro di sistema](security-and-the-registry.md)
