---
title: 'Procedura: aggiungere un riferimento a un assembly con nome sicuro'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f78fff50d1a227061076790ad77f17debe3f690
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-reference-a-strong-named-assembly"></a>Procedura: aggiungere un riferimento a un assembly con nome sicuro
Il processo per la creazione di riferimenti a tipi o risorse in un assembly con nome sicuro è solitamente trasparente all'utente. È possibile creare i riferimenti in fase di compilazione (associazione anticipata) o in fase di esecuzione.  
  
 Un riferimento in fase di compilazione viene creato quando si indica al compilatore che l'assembly contiene riferimenti espliciti a un altro assembly. Quando si usano i riferimenti in fase di compilazione, il compilatore riceve automaticamente la chiave pubblica dell'assembly con nome sicuro di destinazione e inserisce la chiave nel riferimento dell'assembly in fase di compilazione.  
  
> [!NOTE]
>  Gli assembly con nome sicuro possono usare solo tipi da altri assembly con nome sicuro. In caso contrario, la sicurezza dell'assembly con nome sicuro risulterebbe compromessa.  
  
### <a name="to-make-a-compile-time-reference-to-a-strong-named-assembly"></a>Per creare un riferimento in fase di compilazione a un assembly con nome sicuro  
  
1.  Al prompt dei comandi digitare il seguente comando:  
  
     \<*comando compilatore*> **/reference:**\<*nome assembly*>  
  
     In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato e *nome assembly* è il nome dell'assembly con nome sicuro a cui viene fatto riferimento. È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **/t:library** per la creazione di un assembly di librerie.  
  
 L'esempio seguente crea un assembly denominato `myAssembly.dll` che fa riferimento a un assembly con nome sicuro denominato `myLibAssembly.dll` da un modulo di codice denominato `myAssembly.cs`.  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### <a name="to-make-a-run-time-reference-to-a-strong-named-assembly"></a>Per creare un riferimento in fase di esecuzione a un assembly con nome sicuro  
  
1.  Quando si crea un riferimento in fase di esecuzione a un assembly con nome sicuro, ad esempio usando il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, è necessario usare il nome visualizzato dell'assembly con nome sicuro a cui viene fatto riferimento. La sintassi di un nome visualizzato è la seguente:  
  
     \<*nome assembly*>**,** \<*numero versione*>**,** \<*cultura*>**,** \<*token chiave pubblica*>  
  
     Ad esempio:  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     In questo esempio `PublicKeyToken` è il token di chiave pubblica in formato esadecimale. Se non è presente alcun valore relativo alle impostazioni cultura, usare `Culture=neutral`.  
  
 L'esempio di codice seguente illustra come usare queste informazioni con il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.  
  
 [!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)]
 [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)]
 [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]  
  
 È possibile stampare il formato esadecimale della chiave pubblica e del token di chiave pubblica per un assembly specifico usando il comando [Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) seguente:  
  
 **sn -Tp \<** *assembly* **>**  
  
 Se è presente un file di chiave pubblica, è possibile usare il comando seguente (si noti la differenza tra maiuscole e minuscole nell'opzione della riga di comando):  
  
 **sn -tp \<** *assembly* **>**  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione e utilizzo degli assembly con nome sicuro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
