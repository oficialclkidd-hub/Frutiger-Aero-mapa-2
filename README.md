-- 🌆 ULTRA REALISTIC CITY GRAPHICS (NO SOUND)
-- By ChatGPT

local Lighting = game:GetService("Lighting")

-------------------------------------------------
-- ENGINE
-------------------------------------------------
Lighting.Technology = Enum.Technology.Future
Lighting.GlobalShadows = true
Lighting.ClockTime = 13.5
Lighting.Brightness = 3
Lighting.ExposureCompensation = 0.4

Lighting.EnvironmentDiffuseScale = 1
Lighting.EnvironmentSpecularScale = 1

Lighting.Ambient = Color3.fromRGB(140,140,160)
Lighting.OutdoorAmbient = Color3.fromRGB(160,160,180)

-------------------------------------------------
-- SKY ATMOSPHERE (AZUL REALISTA)
-------------------------------------------------
local atm = Instance.new("Atmosphere", Lighting)
atm.Density = 0.25
atm.Offset = 0.1
atm.Color = Color3.fromRGB(170,200,255)
atm.Decay = Color3.fromRGB(100,130,200)
atm.Glare = 0.3
atm.Haze = 1

-------------------------------------------------
-- COLOR CINEMATIC CLEAN
-------------------------------------------------
local cc = Instance.new("ColorCorrectionEffect", Lighting)
cc.Brightness = 0.05
cc.Contrast = 0.2
cc.Saturation = 0.05
cc.TintColor = Color3.fromRGB(230,240,255)

-------------------------------------------------
-- BLOOM HD
-------------------------------------------------
local bloom = Instance.new("BloomEffect", Lighting)
bloom.Intensity = 0.6
bloom.Size = 32
bloom.Threshold = 1

-------------------------------------------------
-- SUN RAYS SOFT
-------------------------------------------------
local sun = Instance.new("SunRaysEffect", Lighting)
sun.Intensity = 0.08
sun.Spread = 0.9

-------------------------------------------------
-- FUTURISTIC CLOUDS
-------------------------------------------------
local clouds = Instance.new("Clouds", Lighting)
clouds.Cover = 0.35
clouds.Density = 0.7
clouds.Color = Color3.fromRGB(255,255,255)

-------------------------------------------------
-- MAP MATERIAL UPGRADE
-------------------------------------------------
for _, obj in pairs(workspace:GetDescendants()) do
    if obj:IsA("BasePart") then
        pcall(function()
            obj.Material = Enum.Material.SmoothPlastic
            obj.Reflectance = 0.15
        end)
    end
end

-------------------------------------------------
print("🌆 Gráficos ultra realistas estilo cidade futurista ativados!")
