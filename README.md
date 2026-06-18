local CalmLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/IcantAffordSynapse/calmlib/refs/heads/main/src.lua"))()

local window = CalmLib:win("sub 2 igotraidedd")
local section1 = window:tab("Spam", "rbxassetid://109121102062195")

getgenv().spamming = false
getgenv().spammingShop = false

section1:toggle("autoclick", false, function(bool)
    getgenv().spamming = bool
    if not getgenv().spamming then return end
    task.spawn(function()
        while getgenv().spamming do
            local Event = game:GetService("ReplicatedStorage").LarpRE
            Event:FireServer(
                CFrame.new(4.1628642082214, 3.9999988079071, -31.459587097168, -0.99790507555008, 0, -0.064695082604885, 0, 1, 0, 0.064695082604885, 0, -0.99790507555008)
            )
            task.wait()
        end
    end)
end)

section1:toggle("Spam upgrades", false, function(bool)
    getgenv().spammingShop = bool
    if not getgenv().spammingShop then return end
    task.spawn(function()
        while getgenv().spammingShop do
            local Event = game:GetService("ReplicatedStorage").ShopRE
            Event:FireServer("LarpGain", true)
            task.wait()
        end
    end)
end)
