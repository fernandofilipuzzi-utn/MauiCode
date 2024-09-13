dotnet new maui -n MauiQR

dotnet clean
dotnet restore
dotnet build
dotnet build -f net8.0-android
dotnet publish -f:net8.0-android -c:Release -o ./publish --self-contained

dotnet add package BarcodeScanner.Mobile.Maui --prerelease -s=https://api.nuget.org/v3/index.json
dotnet add package Microsoft.Maui.Controls.Compatibility --prerelease -s=https://api.nuget.org/v3/index.json


 dotnet build -f net8.0-android34.0
dotnet publish -f:net8.0-android34.0 -c:Release -o ./publish --self-contained
git pull origin main --rebase

# dependencias duplicadas
<PackageReference Include="SomePackage">
    <ExcludeAssets>all</ExcludeAssets>
</PackageReference>


<PropertyGroup Condition="'$(Configuration)|$(TargetFramework)|$(Platform)'=='Debug|net8.0-android34.0|AnyCPU'">
  <AndroidUseAapt2>True</AndroidUseAapt2>
  <AndroidCreatePackagePerAbi>False</AndroidCreatePackagePerAbi>
  <AndroidPackageFormat>apk</AndroidPackageFormat>
</PropertyGroup>


git init 
git remote add origin https://github.com/fernandofilipuzzi-utn/MauiCode.git
git pull origin main --rebase
git config user.name fernandofilipuzzi-utn
git add *
git commit -m "."
git push --set-upstream origin main