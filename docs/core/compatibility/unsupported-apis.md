---
title: API non supportate in .NET Core
titleSuffix: ''
description: Informazioni sulle API del .NET Framework che generano sempre un'eccezione in .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: 941e9149c7679afe4a888149108d0a9a28e5e7ab
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794598"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a>API che generano sempre eccezioni in .NET Core

Le API seguenti genereranno sempre un' <xref:System.PlatformNotSupportedException> operazione in .NET Core su tutti o un subset di piattaforme.

Questo articolo organizza i membri API interessati in base allo spazio dei nomi.

> [!NOTE]
>
> - Questo articolo è un lavoro in corso. Non si tratta di un elenco completo di API che generano eccezioni in .NET Core.
> - Questo articolo non include le implementazioni esplicite dell'interfaccia per la serializzazione binaria generata in .NET Core. Per altre informazioni, vedere [serializzazione binaria in .NET Core](../../standard/serialization/binary-serialization.md#net-core).

## <a name="system"></a>Sistema

| Membro | Piattaforme generate |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | Tutti |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | Tutti |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | Tutti |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | Tutti |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | Tutti |

## <a name="systemcodedomcompiler"></a>System.CodeDom.Compiler

| Membro | Piattaforme generate |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | Tutti |

## <a name="systemcollectionsspecialized"></a>System.Collections.Specialized

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | Tutti |

## <a name="systemconfiguration"></a>System.Configuration

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>(tutti i membri) | Tutti |

## <a name="systemconsole"></a>System.Console

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Console.BufferHeight?displayProperty=nameWithType>(solo set) | Linux e macOS |
| <xref:System.Console.BufferWidth?displayProperty=nameWithType>(solo set) | Linux e macOS |
| <xref:System.Console.CursorSize?displayProperty=nameWithType>(solo set) | Linux e macOS |
| <xref:System.Console.CursorVisible?displayProperty=nameWithType>(solo Get) | Linux e macOS |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Console.Title?displayProperty=nameWithType>(solo Get) | Linux e macOS |
| <xref:System.Console.WindowHeight?displayProperty=nameWithType>(solo set) | Linux e macOS |
| <xref:System.Console.WindowLeft?displayProperty=nameWithType>(solo set) | Linux e macOS |
| <xref:System.Console.WindowTop?displayProperty=nameWithType>(solo set) | Linux e macOS |
| <xref:System.Console.WindowWidth?displayProperty=nameWithType>(solo set) | Linux e macOS |

## <a name="systemdatacommon"></a>System.Data.Common

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType>(genera <xref:System.NotSupportedException>) | Tutti |

## <a name="systemdiagnosticsprocess"></a>System.Diagnostics.Process

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>(solo set) | Linux |
| <xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>(solo set) | Linux |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | macOS |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(solo set) | Linux e macOS |
| <xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>(solo Get) | macOS |
| <xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>(solo set) | Linux e macOS |

## <a name="systemio"></a>System.IO

| Membro | Piattaforme generate |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |

## <a name="systemiopipes"></a>System.IO.Pipes

| Membro | Piattaforme generate |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>(solo set) | Linux e macOS |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | Linux e macOS |

## <a name="systemmedia"></a>System. Media

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |

## <a name="systemnet"></a>System.Net

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | Tutti |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | Tutti |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | Tutti |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |

## <a name="systemnetnetworkinformation"></a>System.Net.NetworkInformation

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | Windows (UWP) |

## <a name="systemnetsockets"></a>System.Net.Sockets

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | Tutti |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | Tutti |

## <a name="systemnetwebsockets"></a>System.Net.WebSockets

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | Tutti |

## <a name="systemreflection"></a>System.Reflection

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | Tutti |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | Tutti |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | Tutti |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | Tutti |

## <a name="systemruntimecompilerservices"></a>System.Runtime.CompilerServices

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | Tutti |

## <a name="systemruntimeinteropservices"></a>System.Runtime.InteropServices

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | Tutti |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | Tutti |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | Tutti |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | Tutti |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | Linux e macOS |

## <a name="systemruntimeserialization"></a>System.Runtime.Serialization

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | Tutti |

## <a name="systemsecurity"></a>System.Security

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | Tutti |

## <a name="systemsecurityclaims"></a>System.Security.Claims

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | Tutti |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | Tutti |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |

## <a name="systemsecuritycryptography"></a>System.Security.Cryptography

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | Linux e macOS |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | Tutti |

## <a name="systemsecuritycryptographypkcs"></a>System.Security.Cryptography.Pkcs

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | Tutti |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | Tutti |

## <a name="systemsecuritycryptographyx509certificates"></a>System.Security.Cryptography.X509Certificates

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>(solo set) | Tutti |

## <a name="systemsecurityauthenticationextendedprotection"></a>System.Security.Authentication.ExtendedProtection

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |

## <a name="systemsecuritypolicy"></a>System. Security. Policy

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |

## <a name="systemserviceprocessservicecontroller"></a>System.ServiceProcess.ServiceController

| Membro | Piattaforme generate |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Tutti |

## <a name="systemtextregularexpressions"></a>System.Text.RegularExpressions

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | Tutti |

## <a name="systemthreading"></a>System.Threading

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Tutti |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | Tutti |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | Tutti |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | Tutti |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | Tutti |

## <a name="systemxml"></a>System.Xml

| Membro | Piattaforme generate |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | Tutti |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | Tutti |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | Tutti |

## <a name="see-also"></a>Vedere anche

- [Modifiche di rilievo per la migrazione da .NET Framework a .NET Core](fx-core.md)
- [Serializzazione binaria in .NET Core](../../standard/serialization/binary-serialization.md#net-core)
- [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md)
