---
title: 'Procedura: Eliminare una chiave del Registro di sistema'
ms.date: 07/20/2015
f1_keywords:
- vb.DeleteSetting
helpviewer_keywords:
- GetSetting function [Visual Basic]
- registry [Visual Basic], deleting values
- GetAllSettings function
- registry keys [Visual Basic], deleting
- registry [Visual Basic], deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
ms.openlocfilehash: f38301a3a717a35b98e55804d6435d046bbbbab4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345645"
---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a><span data-ttu-id="9efb3-102">Procedura: eliminare una chiave del Registro di sistema in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9efb3-102">How to: Delete a Registry Key in Visual Basic</span></span>

<span data-ttu-id="9efb3-103">È possibile usare i metodi <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> e <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> per eliminare le chiavi del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="9efb3-103">The <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> and <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> methods can be used to delete registry keys.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="9efb3-104">Procedura</span><span class="sxs-lookup"><span data-stu-id="9efb3-104">Procedure</span></span>  
  
#### <a name="to-delete-a-registry-key"></a><span data-ttu-id="9efb3-105">Per eliminare una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="9efb3-105">To delete a registry key</span></span>  
  
- <span data-ttu-id="9efb3-106">Usare il metodo `DeleteSubKey` per eliminare una chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="9efb3-106">Use the `DeleteSubKey` method to delete a registry key.</span></span> <span data-ttu-id="9efb3-107">Questo esempio elimina la chiave Software/TestApp nell'hive CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="9efb3-107">This example deletes the key Software/TestApp in the CurrentUser hive.</span></span> <span data-ttu-id="9efb3-108">È possibile impostarlo nel codice sulla stringa appropriata oppure basarsi sulle informazioni specificate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9efb3-108">You can change this in the code to the appropriate string, or have it rely on user-supplied information.</span></span>  
  
     [!code-vb[VbResourceTasks#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a><span data-ttu-id="9efb3-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="9efb3-109">Robust Programming</span></span>  

 <span data-ttu-id="9efb3-110">Il metodo `DeleteSubKey` restituisce una stringa vuota se la coppia chiave/valore non esiste.</span><span class="sxs-lookup"><span data-stu-id="9efb3-110">The `DeleteSubKey` method returns an empty string if the key/value pair does not exist.</span></span>  
  
 <span data-ttu-id="9efb3-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="9efb3-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="9efb3-112">Il nome della chiave è `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="9efb3-112">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="9efb3-113">L'utente non è autorizzato a eliminare le chiavi del Registro di sistema (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="9efb3-113">The user does not have permissions to delete registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="9efb3-114">Il nome della chiave supera il limite di 255 caratteri (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="9efb3-114">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="9efb3-115">La chiave del Registro di sistema è di sola lettura (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="9efb3-115">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9efb3-116">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9efb3-116">.NET Framework Security</span></span>  

 <span data-ttu-id="9efb3-117">Le chiamate al Registro di sistema hanno esito negativo se non sono concesse autorizzazioni sufficienti in fase di esecuzione (<xref:System.Security.Permissions.RegistryPermission>) o se, in base a quanto determinato dagli ACL, l'utente non usa l'accesso corretto per la creazione o la scrittura nelle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9efb3-117">Registry calls fail if either sufficient run-time permissions are not granted (<xref:System.Security.Permissions.RegistryPermission>) or if the user does not have the correct access (as determined by the ACLs) for creating or writing to settings.</span></span> <span data-ttu-id="9efb3-118">Ad esempio, un'applicazione locale che ha l'autorizzazione di sicurezza dall'accesso di codice potrebbe non avere l'autorizzazione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9efb3-118">For example, a local application that has the code access security permission might not have operating system permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efb3-119">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9efb3-119">See also</span></span>

- <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>
- <xref:Microsoft.Win32.RegistryKey>
- [<span data-ttu-id="9efb3-120">Sicurezza e Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="9efb3-120">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)
- [<span data-ttu-id="9efb3-121">Lettura e scrittura nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="9efb3-121">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
