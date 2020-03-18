---
title: 'Procedura: fare riferimento a un assembly con nome sicuroHow to: Reference a strong-named assembly'
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: adda4ed2ab5c59e3518b8e724044529a79840ad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156478"
---
# <a name="how-to-reference-a-strong-named-assembly"></a>Procedura: fare riferimento a un assembly con nome sicuroHow to: Reference a strong-named assembly
Il processo per la creazione di riferimenti a tipi o risorse in un assembly con nome sicuro è solitamente trasparente all'utente. È possibile creare i riferimenti in fase di compilazione (associazione anticipata) o in fase di esecuzione.  
  
Un riferimento in fase di compilazione si verifica quando si indica al compilatore che l'assembly da compilare fa riferimento in modo esplicito a un altro assembly. Quando si usano i riferimenti in fase di compilazione, il compilatore riceve automaticamente la chiave pubblica dell'assembly con nome sicuro di destinazione e inserisce la chiave nel riferimento dell'assembly in fase di compilazione.
  
> [!NOTE]
> Gli assembly con nome sicuro possono usare solo tipi da altri assembly con nome sicuro. In caso contrario, la sicurezza dell'assembly con nome sicuro risulterebbe compromessa.  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a>Creare un riferimento in fase di compilazione a un assembly con nome sicuroMake a compile-time reference to a strong-named assembly  

Al prompt dei comandi digitare il comando seguente:  

\<*comando*> del compilatore **/reference:**\<*nome dell'assembly*>  

In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato e *nome assembly* è il nome dell'assembly con nome sicuro a cui viene fatto riferimento. È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **/t:library** per la creazione di un assembly di librerie.  

Nell'esempio riportato di seguito viene creato un assembly denominato *myAssembly.dll* che fa riferimento a un assembly con nome sicuro denominato *myLibAssembly.dll* da un modulo di codice denominato *myAssembly.cs*.  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a>Creare un riferimento in fase di esecuzione a un assembly con nome sicuroMake a run-time reference to a strong-named assembly  
  
Quando si crea un riferimento in fase di esecuzione a <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> un <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> assembly con nome sicuro, ad esempio utilizzando il metodo o , è necessario utilizzare il nome visualizzato dell'assembly con nome sicuro a cui si fa riferimento. La sintassi di un nome visualizzato è la seguente:  

\<*nome*>dell'assembly **,** \< *numero*>di versione **,** \< *impostazioni cultura*>**,** \< *token di chiave pubblica*>  

Ad esempio:  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

In questo esempio `PublicKeyToken` è il token di chiave pubblica in formato esadecimale. Se non è presente alcun valore relativo alle impostazioni cultura, usare `Culture=neutral`.  

L'esempio di codice seguente illustra come usare queste informazioni con il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.  

```cpp
Assembly^ myDll =
    Assembly::Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```csharp
Assembly myDll =
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```vb
Dim myDll As Assembly = _
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1")
```

È possibile stampare il formato esadecimale della chiave pubblica e del token di chiave pubblica per un assembly specifico usando il comando [Nome sicuro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) seguente:  

**Sn \< -Tp** *assemblaggio***>**  

Se è presente un file di chiave pubblica, è possibile usare il comando seguente (si noti la differenza tra maiuscole e minuscole nell'opzione della riga di comando):  

**sn -tp \<** *file di chiave pubblica* **>**  

## <a name="see-also"></a>Vedere anche

- [Creare e usare gli assembly con nome sicuro](create-use-strong-named.md)
