### <a name="xmlserializer-serializes-fields-differently-in-net-framework-45"></a><span data-ttu-id="ecb72-101">Element XmlSerializer serializuje pola inaczej w programie .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ecb72-101">XmlSerializer serializes fields differently in .NET Framework 4.5</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ecb72-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ecb72-102">Details</span></span>|<span data-ttu-id="ecb72-103">Zmiany w <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> w programie .NET Framework 4.5 spowodował pola mają być inaczej sformatowane serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="ecb72-103">Changes in the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> in .NET Framework 4.5 caused fields to be formatted differently in the serialized XML.</span></span>|
|<span data-ttu-id="ecb72-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="ecb72-104">Suggestion</span></span>|<span data-ttu-id="ecb72-105">Ten problem został rozwiązany w aktualizacja obsługi programu .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="ecb72-105">This behavior was corrected in a servicing update of .NET Framework 4.5.</span></span> <span data-ttu-id="ecb72-106">Zaktualizuj .NET Framework 4.5, lub uaktualnienia programu .NET Framework 4.5.1 lub nowszej, aby rozwiązać ten problem.</span><span class="sxs-lookup"><span data-stu-id="ecb72-106">Please update the .NET Framework 4.5, or upgrade to .NET Framework 4.5.1 or later, to fix this issue.</span></span> <span data-ttu-id="ecb72-107">Można również następujące ustawienia konfiguracji zostaną przywrócone do 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> zachowanie:</span><span class="sxs-lookup"><span data-stu-id="ecb72-107">Alternatively, the following config setting will revert to 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> behavior:</span></span><pre><code>&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="ecb72-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="ecb72-108">Scope</span></span>|<span data-ttu-id="ecb72-109">Główne</span><span class="sxs-lookup"><span data-stu-id="ecb72-109">Major</span></span>|
|<span data-ttu-id="ecb72-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="ecb72-110">Version</span></span>|<span data-ttu-id="ecb72-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ecb72-111">4.5</span></span>|
|<span data-ttu-id="ecb72-112">Typ</span><span class="sxs-lookup"><span data-stu-id="ecb72-112">Type</span></span>|<span data-ttu-id="ecb72-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="ecb72-113">Runtime</span></span>|
|<span data-ttu-id="ecb72-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ecb72-114">Affected APIs</span></span>|<ul><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream%2CSystem.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter%2CSystem.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object%2CSystem.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces%2CSystem.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces%2CSystem.String%2CSystem.String)?displayProperty=nameWithType></li></ul>|
