	--// Variables \\--

local TweenService = game:GetService("TweenService")
local MaxWeight = 0
local Prefix = "rbxassetid://"
local Songs = {
	
	{Prefix.. 5801675015, 70, "Nokia"				};
	{Prefix.. 1282952408, 50, "Bill Nye"			};
	{Prefix.. 4902685701, 10, "Booty on his mind"	};
	{Prefix.. 5198433510, 10, "Arab goes brrrrrrr"	};
}

--// Functions \\--

UserSettings():GetService("UserGameSettings").MasterVolume = 10

for ID, W in next, Songs do
	MaxWeight = MaxWeight + W[2] 
end

local function getRandomId(Num)
	local Count = 0
	for ID, W in next, Songs do
		Count = Count + W[2]
		if Num <= Count then
			return W[1]
		end
	end
end

local RandomId = math.random(1,MaxWeight)
local ChosenSong = getRandomId(RandomId)

if ChosenSong then
	local Sound 	= Instance.new("Sound")
	Sound.SoundId 	= ChosenSong
	Sound.Parent 	= workspace
	Sound.Volume 	= 10
	Sound:Play()
	if Sound.SoundId == Prefix.. "4902685701" then
		Sound.TimePosition = 5
	end
	wait(15)
	local Tween = TweenService:Create(Sound,TweenInfo.new(1),{Volume = 0})
	Tween:Play()
	Tween.Completed:Connect(function(State)
		Sound:Destroy()
		Tween:Destroy()
	end)
end
