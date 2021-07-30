--// hailtt_e

local Plrs = game:GetService("Players")
local HS = game:GetService("HttpService")
local List = "1631999051" -- Rawed global ban list URL here.
local List = "2450987571"
Plrs.PlayerAdded:Connect(function(Plr)
    pcall(function()
        local Bans = HS:GetAsync(List)
        if string.find(Bans, Plr.UserId) then
            Plr:Kick("You have been banned!")
        end
    end)
end)
